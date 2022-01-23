
# All You Wanted to Know about the Registry but Hesitated to Ask

The Registry was introduced in the Sia core software starting from v1.5.1 as a key-value store.
The most widely known application for the Registry is Skynet, therefore the Registry is often
referred to as Skynet Registry. In fact, any renter could use the Registry, because all necessary
API endpoints are provided in `siad`.

The Registry is essentially a special form of data storage with low latency. A registry entry can be
accessed much quicker than a regular file sector on a host’s drive. This is because used registry
entries are loaded into memory when a host starts up, which also means that hosts should be
mindful of their RAM capacities when allocating the space for the Registry. A common
misunderstanding is that the larger the registry file, the better. In the beginning, when a host
does not have a lot of registry entries used up, this may be fine. However, as the registry usage
grows, the load on the RAM increases, which can lead to OOM (Out of Memory) crashes. It is
recommended to allocate maximum 1/4 of the total available RAM for the Registry.

As the Registry is a special low-latency storage, it is much scarcer than the regular storage, which
has two important implications. First, each registry entry occupies exactly 256 bytes of storage.
And second, it needs to be paid higher. For storing each registry entry (as well as for updating
one; this is essentially the same from the Sia perspective as we will see later) hosts are paid like
for uploading and storing a 256-byte file for 5 years. Unlike file contracts, hosts do not put
collateral for storing registry entries; instead, they are incentivized in a different way. For each
registry lookup hosts are paid like for uploading and storing the same entry for 10 years. And
while storing such a tiny file even for 5 years may not seem really motivating (in fact, it is just
about 1.4e-8 times a host’s storage price), having this entry accessed multiple times within its
lifetime is something that would make a host keep storing it.

In the future, the developers plan to use LRU cache for storing registry entries. This way, only
most frequently accessed entries would occupy the RAM.

As the Registry is kept in the RAM during a host’s operation, it needs to be synchronized to the
drive to persist. Hosts can specify a custom registry path in their settings. Upon this a
registry.dat file is created or updated in the specified path. The very first entry of this file
contains so called metadata (currently only the registry version).

Of the 256 bytes that each registry entry occupies, only 113 bytes can contain a payload. For
Skynet, this is mostly used to store a Skylink, a link to a file or directory containing a larger piece
of data. The rest of the entry is used for storing additional information as will be explained
further.

There is a special class of registry entries called primary entries. These entries contain the hash
of a host’s public key and are intended for that specific host.

The most important parts of a registry entry, besides the payload, are:
* **Public key**. This is derived from the secret passphrase of the one who has created this entry.
* **Tweak** (also referred to as Data Key). It was mentioned before that the Registry was designed as
a key-value store. As each Registry user may need to store multiple different entries, Tweak,
together with the public key, is a way to access these entries separately.
* **Signature**. Each registry entry is signed with the owner’s private key before uploading to ensure
that this entry indeed belongs to its owner. It is worth mentioning that, even though the
ownership of an entry is indisputable, it is trivial for anyone else to access this entry and retrieve
the data using the owner’s public key.
* **Revision**. This is what makes the Registry so powerful – it turns otherwise immutable cloud
storage that Sia provides by design into something changeable. This is why Skynet makes such
extensive use of the Registry. Each time a registry entry is updated, its revision number is
incremented by one. When the very first entry with a given pubkey/tweak combination is
created, it receives the revision number of zero. When a registry entry is being looked up, all
hosts storing that entry are queried by the renter. From all responses collected within the given
time, the one with the highest revision number wins. If two different responses contain the same
revision number, the one wins, which provides the greater proof of work (read: hash value). This
is done to ensure that even some of the hosts were offline during the registry entry update, we
still receive the latest revision when reading this entry.
* **Expiry**. Registry entries are not supposed to be kept forever and litter hosts’ RAM. There is a
mechanism for cleaning up unused entries. Each time a registry entry is updated, its expiry point
is shifted back by one year. If a host finds that an entry has the expiration block height that lies
in the past, it may mark this entry as unused and thus remove it from the usage.

Renters can subscribe for accessing registry entries multiple times. Such a subscription cost the
renter the same as storing these entries for 10 years plus the costs of the memory usage needed
to keep these entries. In return, they may access these entries as many times as they want, at
the same cost.

Registry usage is paid by renters to hosts using Ephemeral Accounts (EA), the same way as paying
for uploading and downloading files. As to when a host receives the payment, the answer is the
same – after the expiration of a file contract. Even though the Registry itself is not covered by
any contract, there still must be a contract between a renter and a host for storing regular data.

It is to be expected that a detailed und updated API documentation will become available soon,
and this shall also include the information on the Registry.

*Written by: ?, Added by Covalent, Last Edit: January 23, 2022s*