# TCP/IP
chap 06

## Delivery
- Direct Delivery: 송신자와 수신자가 같은 네트워크 안에 있을 때 직접 전달
- Indirect Delivery: 송신자와 수신자가 다른 네트워크에 있을 때 라우터를 거쳐 전달
<br>

## Forwarding
- 포워딩이란? <br>
    + 도착한 패킷을 목적지로 가는 경로상(next hop)으로 보내는 일을 말한다. <br><br>

- 포워딩 방식
    - 목적지 주소 기반(Forwarding based on destination address)
    - 라벨 기반 포워딩(Forwarding based on label)

### 목적지 주소 기반 포워딩
- next-hop method <br>
    + 목적지 호스트가 다른 네트워크에 있을 때, 라우터가 최종 목적지까지 직접 가지 않고, <br>
    중간 경로의 다음 라우터(next hop router)에게 패킷을 넘기는 방식 <br><br>

    ![next-hop](./src/img1.png)
    <br>
    ![next-hop_table](./src/img2.png)
    <br><br>

- Network-specific method
    + 호스트가 아닌 네트워크 전체를 대상으로 하는 방법 <br><br>

    ![net-spec](./src/img3.png)
    <br><br>
