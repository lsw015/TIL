# Graph

노드(네트워크 또는 데이터 구조를 구성하는 각각의 개체)와 노드를 연결하는 간선(edge)을 하나로 모아 놓은 자료 구조

## 용어

- 정점(vertex): 네트워크 또는 데이터 구조를 구성하는 각각의 개체 (node 라고도 부름)
- 간선(arch): 버텍스를 연결하는 선 (edge 라고도 부름)
- 인접 정점(adjacent vertex): 아크에 의해 직접 연결된 버텍스
- 버텍스의 차수(degree): 무방향 그래프에서 하나의 버텍스에 인접한 버텍스의 수
- 진입 차수(in-degree): 다른 버텍스에서부터 오는 아크의 개수
- 진출 차수(out-degree): 다른 버텍스로 가는 아크의 개수
- 경로 길이(path length): 경로를 구성하는 데 사용된 아크의 수
- 단순 경로(simple path): 경로 중에서 반복되는 버텍스가 없는 경우
- 사이클(cycle): 단순 경로의 시작 버텍스와 종료 버텍스가 동일한 경우

## 오일러 경로(Eulerian tour)

그래프에 존재하는 모든 아크을 한 번만 통과하면서 처음 버텍스으로 되돌아오는 경로를 말한다.
그래프의 모든 버텍스에 연결된 아크의 개수가 짝수일 때만 오일러 경로가 존재한다.

## 방향 그래프 vs 무방향 그래프

<img src="https://cdn.filepicker.io/api/file/ASqFe9MSQXqzoZthyThq"/>

왼쪽은 방향 그래프이고, 오른쪽은 무방향 그래프이다. 방향 그래프는 방향을 나타내는 화살표가 있지만 무방향 그래프는 없다 트리도 방향 그래프이다

트리의 노드가 하나의 In-degree만 가지는 반면, 그래프의 버텍스는 하나 이상의 In-degree를 가질 수 있다

## 완전 그래프

<img src='https://t1.daumcdn.net/cfile/tistory/99B299345B5408DA18' />

모든 버텍스가 아크로 연결된 그래프를 완전 그래프라고 부르고 그래프의 부분집합을 부분 그래프라고 부른다