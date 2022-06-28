
  ================================================================
  ##  제출용 - 1. MSA 아키텍처 구성도
<img width="800" alt="01  MSA Architecture" src="https://user-images.githubusercontent.com/9667747/176066481-7bcd1d7a-6336-404f-9c94-b12c3bfa1954.png">
  
  ================================================================
  
  ##  제출용 - 2. 파이프라인 구성도
  <img width="737" alt="02  Pipeline Diagram" src="https://user-images.githubusercontent.com/9667747/176067429-dbc5274f-6db9-4379-9290-b12a6a61d685.png">

   
  ================================================================
  
  ##  제출용 - 3. MSA Orechestration
- 상품등록
	http POST http://aa994d744289c4cf8bbf97e4aef89191-509785601.ap-northeast-1.elb.amazonaws.com:8080/inventories productId=1001 productName=TV stock=100
	root@labs--183126647:/home/project/order# http POST http://aa994d744289c4cf8bbf97e4aef89191-509785601.ap-northeast-1.elb.amazonaws.com:8080/inventorie
productId=1001 productName=TV stock=100
	HTTP/1.1 201 Created			
	Content-Type: application	/json			
	Date: Thu, 23 Jun 2022 01	:58:1		6 GMT			
	Location: http://aa994d74	4289c		4cf8bbf97e4a	ef89191-50		9785601.ap-northeast-1.elb.amazonaws.com:8080/	inventories/1	
	Vary: Origin			
	Vary: Access-Control-Request-Method			
	Vary: Access-Control-Request-Headers				
	transfer-encoding: chunked			
	
	{
	    "_links": {
	        "inventory": {
	            "href": "http://aa994d744289c4cf8bbf97e4aef89191-509785601.ap-northeast-1.elb.amazonaws.com:8080/inventories/1"
	        },
	        "self": {
	            "href": "http://aa994d744289c4cf8bbf97e4aef89191-509785601.ap-northeast-1.elb.amazonaws.com:8080/inventories/1"
	        }
	    },
	    "productId": "1001",
	    "productName": "TV",
	    "stock": 100
	}
- 주문생성
	http POST http://aa994d744289c4cf8bbf97e4aef89191-509785601.ap-northeast-1.elb.amazonaws.com:8080/orders productId=1001 productName=TV qty=5 customerI
	root@labs--183126647:/home/project/order# http POST http://aa994d744289c4cf8bbf97e4aef89191-509785601.ap-northeast-1.elb.amazonaws.com:8080/orders 
productId=1001 	productName=TV qty=5 customerId=100	
	HTTP/1.1 201 Created	
	Content-Type: application/json	
	Date: Thu, 23 Jun 2022 02:00:43 GMT	
	Location: http://aa994d744289c4cf8b	bf97e4aef89191-509785601.ap-northeast-1.elb.amazonaws.com:8080/orders/1	
	Vary: Origin	
	Vary: Access-Control-Request-Method	
	Vary: Access-Control-Request-Headers	
	transfer-encoding: chunked	
	
	{
	    "_links": {
	        "order": [
	            {
	                "href": "http://aa994d744289c4cf8bbf97e4aef89191-509785601.ap-northeast-1.elb.amazonaws.com:8080/orders/1"
	            },
	            {
	                "href": "http://aa994d744289c4cf8bbf97e4aef89191-509785601.ap-northeast-1.elb.amazonaws.com:8080/orders/1/order"
	            }
	        ],
	        "order cancel": {
	            "href": "http://aa994d744289c4cf8bbf97e4aef89191-509785601.ap-northeast-1.elb.amazonaws.com:8080/orders/1/order cancel"
	        },
	        "self": {
	            "href": "http://aa994d744289c4cf8bbf97e4aef89191-509785601.ap-northeast-1.elb.amazonaws.com:8080/orders/1"
	        }
	    },
	    "customerId": "100",
	    "productId": "1001",
	    "productName": "TV",
	    "qty": 5,
	    "status": null
	}
- 주문취소
	http DELETE http://aa994d744289c4cf8bbf97e4aef89191-509785601.ap-northeast-1.elb.amazonaws.com:8080/orders/1
	root@labs--183126647:/home/project/order# http DELETE http://aa994d744289c4cf8bbf97e4aef89191-509785601.ap-northeast-1.elb.amazonaws.com:8080/orders/1
	HTTP/1.1 204 No Content		
	Date: Thu, 23 Jun 2022 		02:01:46 GMT		
	Vary: Origin		
	Vary: Access-Control-Request-Method
	Vary: Access-Control-Request-Headers
- Kafka 모니터링 : kubectl -n kafka exec -ti my-kafka-0 -- /usr/bin/kafka-console-consumer --bootstrap-server my-kafka:9092 --topic mall --from-beginning

    
  ================================================================
  
  ##  제출용 - 4. Service Mesh
<img width="1358" alt="Istio" src="https://user-images.githubusercontent.com/9667747/176068955-f7703d87-f484-48cf-a1f0-1c1599fe57fa.png">

    
  ================================================================
  
  ##  제출용 - 5. Monitoring (Grafana, Promehteus)
  
  ================================================================
  <img width="1358" alt="Grafana 모니터링-Prometheus" src="https://user-images.githubusercontent.com/9667747/176068079-ffe4d2b5-6bb2-4d79-a709-64fd9cce43bd.png">

  ================================================================
  
  ##  제출용 - 6. Logging (EFK)
  <img width="1419" alt="Logging (EFK)" src="https://user-images.githubusercontent.com/9667747/176068068-ac00d1e3-6a56-49c9-8a23-c0a42a1d618b.png">

  ================================================================

  ================================================================
  
  ##  제출용 - 7. Kafka UI
<img width="1408" alt="Kafka-UI" src="https://user-images.githubusercontent.com/9667747/176069618-d5e53472-909b-4a77-9a4b-094642f0bb90.png">

  ================================================================
