# MerkleTree

Merkle Tree implementation in pure Elixir.

[![Travis](https://img.shields.io/travis/yosriady/merkle_tree.svg?maxAge=2592000)](https://travis-ci.org/yosriady/merkle_tree)
[![Coveralls](https://img.shields.io/coveralls/yosriady/merkle_tree.svg?maxAge=2592000)](https://coveralls.io/github/yosriady/merkle_tree)
[![Hex.pm](https://img.shields.io/hexpm/v/merkle_tree.svg?maxAge=2592000)](https://hex.pm/packages/merkle_tree)

### [Hex](http://hex.pm/packages/merkle_tree)
### [API Documentation](https://hexdocs.pm/merkle_tree/)

## Installation

Add `merkle_tree` to your list of dependencies in `mix.exs`:

```elixir
def deps do
  [{:merkle_tree, "~> 1.0.0"}]
end
```

## Usage

```elixir
iex> f = MerkleTree.new ['a', 'b', 'c', 'd']
%MerkleTree{blocks: ['a', 'b', 'c', 'd'], hash_function: &MerkleTree.Crypto.sha256/1,
      root: %MerkleTree.Node{children: [%MerkleTree.Node{children: [%MerkleTree.Node{children: [],
           value: "ca978112ca1bbdcafac231b39a23dc4da786eff8147c4e72b9807785afee48bb"},
          %MerkleTree.Node{children: [], value: "3e23e8160039594a33894f6564e1b1348bbd7a0088d42c4acb73eeaed59c009d"}],
         value: "62af5c3cb8da3e4f25061e829ebeea5c7513c54949115b1acc225930a90154da"},
        %MerkleTree.Node{children: [%MerkleTree.Node{children: [], value: "2e7d2c03a9507ae265ecf5b5356885a53393a2029d241394997265a1a25aefc6"},
          %MerkleTree.Node{children: [], value: "18ac3e7343f016890c510e93f935261169d9e3f565436429830faf0934f4f8e4"}],
         value: "d3a0f1c792ccf7f1708d5422696263e35755a86917ea76ef9242bd4a8cf4891a"}],
       value: "58c89d709329eb37285837b042ab6ff72c7c8f74de0446b091b6a0131c102cfd"}}
```

## Background

A hash tree or Merkle tree is a tree in which every non-leaf node is labelled with the hash of the labels or values (in case of leaves) of its child nodes. Hash trees are useful because they allow efficient and secure verification of the contents of large data structures. Hash trees are a generalization of hash lists and hash chains.

![](https://upload.wikimedia.org/wikipedia/commons/thumb/9/90/MerkleTree1.svg/800px-MerkleTree1.svg.png)

Hash trees can be used to verify any kind of data stored, handled and transferred in and between computers. Currently the main use of hash trees is to make sure that data blocks received from other peers in a peer-to-peer network are received undamaged and unaltered, and even to check that the other peers do not lie and send fake blocks. Suggestions have been made to use hash trees in trusted computing systems. Hash trees are used in the IPFS and ZFS file systems,  BitTorrent protocol, Apache Wave protocol, Git distributed revision control system, the Bitcoin peer-to-peer network, the Ethereum peer-to-peer network, and a number of NoSQL systems like Apache Cassandra and Riak.

## Running Type Checker

```
mix dialyzer
```

## Contributing

1. Fork it ( http://github.com/Leventhan/merkle_tree/fork )
2. Create your feature branch (`git checkout -b feature/my-new-feature`)
3. Commit your changes (`git commit -am 'Add some feature'`)
4. Push to the branch (`git push origin feature/my-new-feature`)
5. Create a new Pull Request (Remember to squash your commits!)

> Kindly report any found bugs or errors using [the issue tracker](https://github.com/Leventhan/merkle_tree/issues).

## Thanks

**merkle_tree** © 2016+, Yos Riady. Released under the [MIT] License.<br>
Authored and maintained by Yos Riady with help from contributors ([list][contributors]).

> [yos.io](http://yos.io) &nbsp;&middot;&nbsp;
> GitHub [@yosriady](https://github.com/yosriady)

[MIT]: http://mit-license.org/
[contributors]: http://github.com/yosriady/merkle_tree/contributors
