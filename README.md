# **SWE_2021_41_2024_2_week_6**
## **Week 4 Assignment**
 - https://github.com/MinSeok-e/SWE_2021_41_2024_2_week_4


```python
def isHappy(n):
  a=set()


  while n!=1:
     n = sum(int(i)**2 for i in str(n))  #자릿수 합
     if n in a:           #무한 loop 방지
      return False
     a.add(n)

  return True

num=int(input())
ans=isHappy(num)
print(ans)
```

- `Happy Number`를 찾는 알고리즘을 구현한 것이다.\
 먼저, 'Happy number'란 **각 자리수의 제곱의 합**을 계산 하는 과정을 결과값이 1이 나올 때까지 계속 하는 과정을 거쳐서, 결국 **1**이 나오는 수를 'Happy number'라고 한다.\
예를 들자면 19라는 수가 주어질 때,\
첫 단계는, $1^2+9^2=82$ 이다.\
다음은, 8^(2)+2^(2)=**68** 이다.\
다음은, 6^(2)+8^(2)=**100** 이다.\
마지막으로, 1^(2)+0^(2)+0^(2)=0이므로, **19**는 'Happy Number'가 된다.\
우선 n을 매개변수로 받고, return으로 True를 반환하는 함수 *isHappy*를 정의한다.\
a라는 set를 만든다. 그 이유는 결국 나중에 설명하게 될 무한 **loop방지**와 관련이 있다.\
n이라는 input을 받았을 때, n이 1이 되지 않을 때까지 n의 자릿수의 합을 더하는 실행을 반복한다.\
이 때 만약 n=4일 때의 경우를 살펴보면,
4>>37>>58>>89>>145>>42>>20>>4 이 순서로 값이 나와서 결국 4라는 값이 또 나와서 무한으로 loop가 돌아가게 된다.\
이를 방지하고자 자릿수의 합 연산을 한 번씩 할 때마다, 그 나오는 결과 값을 a에 저장하게 된다.\
만약 반복문을 진행하다 a에 이미 저장되어 있던 수가 n이 될 때는 최종 결과가 False가 된다.\
즉, 위의 4의 예시에서 20의 자리수의 합을 계산한 값인 4가 n이 된다면, 4는 이미 제일 처음에 a에 들어갔기 때문에 이는 False가 나오게 된다.\
결국 4는 'Happy Number'가 아니라는 결론이 나오게 된다.\
그 외 코드는 문제에서 1<=n<=2^(31)-1 이라는 범위 제한이 있기 때문에, int를 input으로 받게 되고, 함수의 return값이 된 'Happy Number'인 num이 출력된다.




## Week 5 Assignment


>```bash
>docker exec ossp-container cat /etc/os-release
>```
>- **ossp-container 내의 Linux 시스템의 버전 정보를 확인하기 위한 명령어이다.**\
>output : PRETTY_NAME="Ubuntu 24.04.1 LTS"\
>NAME="Ubuntu"\
>VERSION_ID="24.04"\
>VERSION="24.04.1 LTS (Noble Numbat)"\
>VERSION_CODENAME=noble\
>ID=ubuntu\
>ID_LIKE=debian\
>HOME_URL="https://www.ubuntu.com/"\
>SUPPORT_URL="https://help.ubuntu.com/"\
>BUG_REPORT_URL="https://bugs.launchpad.net/ubuntu/"\
>PRIVACY_POLICY_URL="https://www.ubuntu.com/legal/terms-and-policies/privacy-policy"\
>UBUNTU_CODENAME=noble\
>LOGO=ubuntu-logo

>```bash
>docker exec ossp-container git --version
>```
>- **ossp-container 안에 설치되어 있는 Git의 버전을 확인하기 위한 명령어이다.**\
>output : git version 2.43.0

>```bash
>docker exec ossp-container python3 --version
>```
>- **ossp-container 안에 설치되어 있는 Python3의 버전을 확인하기 위한 명령어이다.**\
>output : Python 3.12.3


>```bash
>docker inspect --format="{{ .HostConfig.Binds }}" ossp-container
>```
>- **ossp-container가 호스트의 어떤 폴더를 사용하고 있는지 확인하기 위한 명령어이다.**\
>output : [./ossp_host_dir:/mnt/ossp_container_dir]







