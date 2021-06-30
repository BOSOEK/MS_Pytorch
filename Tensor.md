# Tensor

> 텐서란? Numpy의 ndarray와 유사하며 __GPU등의 가속기에서 실행__ 할 수 있으며 __자동 미분에 최적화 되있는 데이터 구조__ 이다.

```
import torch
```
![텐서차원](https://user-images.githubusercontent.com/68007145/123546776-0348c180-d799-11eb-9d74-82a5941ce4f2.png)

* ### 텐서 초기화 : *torch.tensor(data)*   
    > *data = [[1, 2], [3,4]]*    
    > *x = torch.tensor(data)*   
* ### 넘파이 배열에서 텐서 초기화 : *torch.from_numpy*   
    > *narray = np.array(data)*   
    > *x = torch.from_numpy(narray)  # 넘파이 배열을 텐서로 변환*   

* ### 텐서에서 텐서 얻기 : 속성은 그대로 값만 변경   
    > *ones = torch.ones_like([[1,2], [3,4]])*   
    ```1,1,1,1로 설정```   
    > *ones = torch.zeros_like([[1,2], [3,4]])*     
    ```0,0,0,0로 설정```   
    > *rand = torch.rand_like([[1,2], [3,4]])*   
    ```0부터 1사이의 랜덤 값으로 설정```
    
    함수에 리스트가 아닌 상수 값을 넣으면 텐서의 형태 지정 가능   
    > *a = torch.ones_like(2, 3)*
    ```
    >>> [[1, 1, 1],
        [1, 1, 1]]
    ```
* ### 텐서의 속성
    * 텐서의 모양(차원) : ```tensor.shape```
    * 텐서 데이터 유형 : ```tensor.dtype```
    * 텐서 장치 : ```tensor.device```
* ### 텐서 작업 : GPU 사용 가능시 GPU 사용
    ```
    if torch.cuda.is_available( )
        tensor = tensor.to('cuda)
    ```
* ### 텐서 결합 : torch.cat()
    
    > *da = torch.ones(4, 4)*   
    > *t = torchc.cat([da, da, da], dim=1)*
    ```
    >>> tensor([[1., 0., 1., 1., 1., 0., 1., 1., 1., 0., 1., 1.],
        [1., 0., 1., 1., 1., 0., 1., 1., 1., 0., 1., 1.],
        [1., 0., 1., 1., 1., 0., 1., 1., 1., 0., 1., 1.],
        [1., 0., 1., 1., 1., 0., 1., 1., 1., 0., 1., 1.]])
    ```
* ### 산술 연산 
    > *torch.add(a1, a2)*  ```# 각각의 요소별 더하기```   
    > *torch.sub(a1, a2)*  ```# 각각의 요소별 빼기```   
    > *torch.mul(a1, a2)*  ```# 각각의 요소별 곱하기```   
    > *torch.div(a1, a2)*  ```# 각각의 요소별 나누기```  
    > *torch.matmul(a1, a2)*  ```# 행렬 곱셈```   