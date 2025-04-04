# 1753번: 최단경로 - `<img src="https://static.solved.ac/tier_small/12.svg" style="height:20px" />` Gold IV

<!-- performance -->

<!-- 문제 제출 후 깃허브에 푸시를 했을 때 제출한 코드의 성능이 입력될 공간입니다.-->

<!-- end -->

## 문제

[문제 링크](https://boj.kr/1753)

<p>방향그래프가 주어지면 주어진 시작점에서 다른 모든 정점으로의 최단 경로를 구하는 프로그램을 작성하시오. 단, 모든 간선의 가중치는 10 이하의 자연수이다.</p>

## 입력

<p>첫째 줄에 정점의 개수 V와 간선의 개수 E가 주어진다. (1 ≤ V ≤ 20,000, 1 ≤ E ≤ 300,000) 모든 정점에는 1부터 V까지 번호가 매겨져 있다고 가정한다. 둘째 줄에는 시작 정점의 번호 K(1 ≤ K ≤ V)가 주어진다. 셋째 줄부터 E개의 줄에 걸쳐 각 간선을 나타내는 세 개의 정수 (u, v, w)가 순서대로 주어진다. 이는 u에서 v로 가는 가중치 w인 간선이 존재한다는 뜻이다. u와 v는 서로 다르며 w는 10 이하의 자연수이다. 서로 다른 두 정점 사이에 여러 개의 간선이 존재할 수도 있음에 유의한다.</p>

## 출력

<p>첫째 줄부터 V개의 줄에 걸쳐, i번째 줄에 i번 정점으로의 최단 경로의 경로값을 출력한다. 시작점 자신은 0으로 출력하고, 경로가 존재하지 않는 경우에는 INF를 출력하면 된다.</p>

## 해결방법

<p>다익스트라 문제이다. 여기서는 dist[] 중 최소값을 찾기 위해 minheap을 이용하였다. 다익스트라 알고리즘에서 dist가 변하는 것을 바로 업데이트 할 수 없기 때문에 fake_dist와 dist[]로 이분화하여 minheap에서 값을 pop 할때 이를 확인하는 lazy update 방식을 이용하였다. 
한편 주석에서 얘기하였듯 간선을 입력을 받을 때마다 update하지 말고 다익스트라에서 업데이트 하는 것이 시간적으로 더 이득이다. 이는 다익스트라의 실행횟수와 간선 입력횟수를 비교해보면 알 수 있다. </p>
