# server-scale-out-study
서비스 규모가 커졌을때, (트래픽이 많아졌을 때) 
서버의 프론트와 백엔드 복제하여 증설하고 
증설했을 때 발생하는 로드벨런싱과 병목현상을 해결해보기 

1. 트래픽 요청 스케줄러 생성  > spring
2. 기존 서비스에 대량 요청 전송  > front-nextjs, back-spring
3. 모니터링 툴로 이를 감시  > prometheus, grafana
4. 어플리케이션을 컨테이너에 올려 증설시키기  > docker swarm, kube?
5. 어플리케이션 증설, 복제시 생기는 병목 현상 관찰  
6. 데이터베이스 증설해보기  > mysql, redis
7. 사용자의 요청을 로드밸런싱 처리 해보기  > docker swarm, kube


aws, cafe24 > 
1. webserver > nginx
2. webserver -> frontend > nextjs
3. webserver -> frontend -> backend > spring
4. (webserver, frontend, backend) >> image >> container >> virtual network connect > docker network or kube service
5. traffic >> network >> Orchestration > docker swarm or kube
