## 목차
1. `Graph`
2. `Graph`의 시간 복잡도
3. `Graph`의 탐색

<br>

### Graph
정점(Vertex)의 모음과 정점과 정점을 잇는 간선(Edge)의 결합

<br>

### Graph의 공간 복잡도
- 인접 행렬(Adjacent Matric) : 정방 행렬을 사용하는 방법
    - 해당하는 위치의 value 값을 통해서 Vertex간의 연결관계를 `O(1)`로 파악 가능
    - 단, 공간 복잡도는 Edge의 개수와는 무관하게 O(V<sup>2</sup>) 
    - 그래프에 간선이 많이 존재하는 `밀집 그래프(Dense Graph)`의 경우 유리함
- 인접 리스트(Adjacent List) : 연결 리스트를 사용하는 방법
    - Vertex의 인접 리스트를 확인해봐야 하므로 Vertex간 연결되어있는지를 각각 확인해야함
    - 공간복잡도는 `O(V+E)`를 갖음
    - 그래프 내에 간선의 숫자가 적은 `희소 그래프(Sparse Graph)`의 경우 유리함

<br>

### Graph의 탐색
> 그래프는 정점의 구성 뿐만 아니라 간선의 연결에도 규칙이 존재하기 때문에 탐색이 복잡하다.  
따라서 그래프의 모든 정점을 탐색하기 위한 방법은 아래 두 가지 알고리즘을 기반으로 한다.

1. 깊이 우선 탐색 (DFS, Depth First Search)
- **그래프 상에 존재하는 임의의 한 정점으로부터 연결되어 있는 한 정점으로만 나아간다** 라는 방법으로 탐색
- 일단 연겨된 정점을 계속 탐색하여, 더 이상 연결된 정점이 없다면 이전 단계의 정점으로 돌아가 다른 정점을 탐색
- `Stack`, 또는 `재귀`를 사용하여 구현 가능
- 시간복잡도는 `O(V+E)`

<br>

2. 너비 우선 탐색 (BFS, Breadth First Search)
- **그래프 상에 존재하는 임의의 한 정점으로부터 연결되어 있는 모든 정점으로 나아간다** 라는 방법으로 탐색
- `Queue`를 사용하여 구현 가능
- 우선 탐색을 시작하는 정점을 큐에 넣음 -> 큐의 값을 꺼내어 해당 정점에 연결되어있는 모든 정점을 다시 큐에 넣으며 탐색 진행
- 시간 복잡도는 `O(V+E)`