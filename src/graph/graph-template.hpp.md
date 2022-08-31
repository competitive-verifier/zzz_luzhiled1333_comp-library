---
data:
  _extendedDependsOn:
  - icon: ':heavy_check_mark:'
    path: src/cpp-template/header/type-alias.hpp
    title: Type alias
  _extendedRequiredBy:
  - icon: ':heavy_check_mark:'
    path: src/graph/dijkstra.hpp
    title: Dijkstra's Algorithm
  - icon: ':heavy_check_mark:'
    path: src/graph/functional-graph-utility.hpp
    title: src/graph/functional-graph-utility.hpp
  - icon: ':heavy_check_mark:'
    path: src/graph/offline-query-lowest-common-ancestor.hpp
    title: src/graph/offline-query-lowest-common-ancestor.hpp
  _extendedVerifiedWith:
  - icon: ':heavy_check_mark:'
    path: test/aoj/grl_1_a.test.cpp
    title: test/aoj/grl_1_a.test.cpp
  - icon: ':heavy_check_mark:'
    path: test/aoj/grl_5_c.test.cpp
    title: test/aoj/grl_5_c.test.cpp
  - icon: ':heavy_check_mark:'
    path: test/atcoder/abc258_e.test.cpp
    title: test/atcoder/abc258_e.test.cpp
  _isVerificationFailed: false
  _pathExtension: hpp
  _verificationStatusIcon: ':heavy_check_mark:'
  attributes:
    links: []
  bundledCode: "#line 2 \"src/graph/graph-template.hpp\"\n\n#line 2 \"src/cpp-template/header/type-alias.hpp\"\
    \n\n#include <cstddef>\n#include <cstdint>\n\nnamespace luz {\n\n  using isize\
    \ = std::ptrdiff_t;\n  using usize = std::size_t;\n\n  using i32 = std::int32_t;\n\
    \  using i64 = std::int64_t;\n  using u32 = std::uint32_t;\n  using u64 = std::uint64_t;\n\
    \n} // namespace luz\n#line 4 \"src/graph/graph-template.hpp\"\n\n#include <cassert>\n\
    #include <vector>\n\nnamespace luz {\n\n  template < typename cost_type >\n  class\
    \ Edge {\n   public:\n    usize from, to;\n    cost_type cost;\n    usize id;\n\
    \    Edge() = default;\n    Edge(usize from_, usize to_, cost_type cost_, usize\
    \ id_)\n        : from(from_),\n          to(to_),\n          cost(cost_),\n \
    \         id(id_) {}\n  };\n\n  template < typename cost_type >\n  using Edges\
    \ = std::vector< Edge< cost_type > >;\n\n  template < typename cost_type >\n \
    \ class Graph {\n   protected:\n    std::vector< std::vector< Edge< cost_type\
    \ > > > g;\n    usize edge_count;\n\n   public:\n    Graph() = default;\n    explicit\
    \ Graph(usize n): g(n), edge_count(0) {}\n\n    usize size() const {\n      return\
    \ g.size();\n    }\n\n    void add_directed_edge(usize from, usize to, cost_type\
    \ cost = 1) {\n      assert(from < size());\n      assert(to < size());\n    \
    \  g[from].emplace_back(from, to, cost, edge_count++);\n    }\n\n    void add_undirected_edge(usize\
    \ u, usize v, cost_type cost = 1) {\n      assert(u < size());\n      assert(v\
    \ < size());\n      g[u].emplace_back(u, v, cost, edge_count);\n      g[v].emplace_back(v,\
    \ u, cost, edge_count++);\n    }\n\n    inline Edges< cost_type > &operator[](const\
    \ usize &v) {\n      return g[v];\n    }\n\n    inline const Edges< cost_type\
    \ > &operator[](\n        const usize &v) const {\n      return g[v];\n    }\n\
    \  };\n\n} // namespace luz\n"
  code: "#pragma once\n\n#include \"src/cpp-template/header/type-alias.hpp\"\n\n#include\
    \ <cassert>\n#include <vector>\n\nnamespace luz {\n\n  template < typename cost_type\
    \ >\n  class Edge {\n   public:\n    usize from, to;\n    cost_type cost;\n  \
    \  usize id;\n    Edge() = default;\n    Edge(usize from_, usize to_, cost_type\
    \ cost_, usize id_)\n        : from(from_),\n          to(to_),\n          cost(cost_),\n\
    \          id(id_) {}\n  };\n\n  template < typename cost_type >\n  using Edges\
    \ = std::vector< Edge< cost_type > >;\n\n  template < typename cost_type >\n \
    \ class Graph {\n   protected:\n    std::vector< std::vector< Edge< cost_type\
    \ > > > g;\n    usize edge_count;\n\n   public:\n    Graph() = default;\n    explicit\
    \ Graph(usize n): g(n), edge_count(0) {}\n\n    usize size() const {\n      return\
    \ g.size();\n    }\n\n    void add_directed_edge(usize from, usize to, cost_type\
    \ cost = 1) {\n      assert(from < size());\n      assert(to < size());\n    \
    \  g[from].emplace_back(from, to, cost, edge_count++);\n    }\n\n    void add_undirected_edge(usize\
    \ u, usize v, cost_type cost = 1) {\n      assert(u < size());\n      assert(v\
    \ < size());\n      g[u].emplace_back(u, v, cost, edge_count);\n      g[v].emplace_back(v,\
    \ u, cost, edge_count++);\n    }\n\n    inline Edges< cost_type > &operator[](const\
    \ usize &v) {\n      return g[v];\n    }\n\n    inline const Edges< cost_type\
    \ > &operator[](\n        const usize &v) const {\n      return g[v];\n    }\n\
    \  };\n\n} // namespace luz\n"
  dependsOn:
  - src/cpp-template/header/type-alias.hpp
  isVerificationFile: false
  path: src/graph/graph-template.hpp
  requiredBy:
  - src/graph/dijkstra.hpp
  - src/graph/functional-graph-utility.hpp
  - src/graph/offline-query-lowest-common-ancestor.hpp
  timestamp: '2022-08-22 18:26:45+09:00'
  verificationStatus: LIBRARY_ALL_AC
  verifiedWith:
  - test/aoj/grl_1_a.test.cpp
  - test/aoj/grl_5_c.test.cpp
  - test/atcoder/abc258_e.test.cpp
documentation_of: src/graph/graph-template.hpp
layout: document
title: "\u30B0\u30E9\u30D5\u69CB\u9020\u4F53"
---

## コンストラクタ
```
Graph(usize n)
```

頂点数 `n` のグラフを定義する。

### 制約
- $0 \leq n$

## size
```
usize size()
```

グラフの頂点数を返す。

## add_directed_edge
```
void add_directed_edge(usize from, usize to, cost_type cost = 1)
```

`from` から `to` へのコスト`cost`の有向辺をグラフに追加する。 `cost` を指定しなかった場合、その辺のコストは 1 になる。

辺には追加された順に 0-indexed で辺番号が割り振られる。

## add_undirected_edge
```
void add_undirected_edge(usize u, usize v, cost_type cost = 1)
```

`u` から `v` へのコスト `cost` の無向辺をグラフに追加する。 `cost` を指定しなかった場合、その辺のコストは 1 になる。

辺には追加された順に 0-indexed で辺番号が割り振られる。

## operator[]
```
(1)       Edges &operator[](const usize &v)
(2) const Edges &operator[](const usize &v) const
```

`v` を始点とする辺のリストを返す。
