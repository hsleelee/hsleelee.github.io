# vsc install

## Linux : Ubuntu 20.04 : Visual Studio Code 설치 방법, 예제, 명령어

### Visual Studio Code를 스냅 패키지로 설치

VS 코드 스냅을 설치하려면 터미널(Ctrl+Alt+T)을 열고 다음 명령을 실행합니다.

```
sudo snap install --classic code
```


### Visual Studio Code를 설치

sudo 권한이 있는 사용자로 다음 명령을 실행하여 패키지 인덱스를 업데이트하고 종속성을 설치합니다.

```
sudo apt update
sudo apt install software-properties-common apt-transport-https wget
```

다음 wget 명령을 사용하여 Microsoft GPG 키를 가져옵니다.

```
wget -q https://packages.microsoft.com/keys/microsoft.asc -O- | sudo apt-key add -
```

그리고 다음을 입력하여 Visual Studio Code 리포지토리를 활성화합니다.

```
sudo add-apt-repository "deb [arch=amd64] https://packages.microsoft.com/repos/vscode stable main"
```

apt 리포지토리를 활성화하면 Visual Studio Code 패키지를 설치합니다.

```
sudo apt install code
```

새 버전이 릴리스되면 데스크톱 표준 소프트웨어 업데이트 도구를 사용하거나 터미널에서 다음 명령을 실행하여 Visual Studio Code 패키지를 업데이트할 수 있습니다.

```
sudo apt update
sudo apt upgrade
```

### Visual Studio Code를 시작

활동 검색란에 "Visual Studio Code"를 입력하고 아이콘을 클릭하여 응용 프로그램을 실행합니다.

터미널 창에서  아래와 같이 입력

```
code
```

VS Code를 처음 시작하면 다음과 같은 창이 나타납니다.

![Pasted image 20231220165413.jpg](./images/Pasted%20image%2020231220165413.jpg) 

이제 새 확장 설치 및 작업 공간 사용자 지정을 시작할 수 있습니다. VS Code에 대한 자세한 내용은 공식 설명서 페이지를 참조하십시오.

## 참조

[https://linuxize.com/post/how-to-install-visual-studio-code-on-ubuntu-20-04/](https://linuxize.com/post/how-to-install-visual-studio-code-on-ubuntu-20-04/)


--------------

# Ubuntu 22.04에 Visual Studio Code를 설치

Visual Studio는 두 가지 방법을 사용하여 Ubuntu 22.04에 설치

## 리포지토리와 키를 추가하여 Visual Studio 코드 설치

Ubuntu 22.04 운영 체제에 코드 편집기를 설치하려면 터미널에서 일련의 명령을 실행해야 합니다. 여기에 이러한 모든 명령이 요약되어 있습니다.

## 1단계: 시스템 업데이트

무엇이든 설치하기 전에 시스템을 업데이트하는 것이 좋은 방법으로 간주되므로 다음 명령을 사용하여 이 작업을 수행할 수 있습니다.

```
$ sudo apt update && sudo apt upgrade -y
```
 
![Pasted image 20231220184515.png](./images/Pasted%20image%2020231220184515.png) 

시스템이 업데이트 및 업그레이드되었습니다.

## 2단계: 패키지 설치

이제 시스템이 업데이트되면 편집기를 설치하기 전에 시스템에 특정 패키지를 설치해야 합니다.

```
$ sudo apt install software-properties-common apt-transport-https wget -y
```

![Pasted image 20231220184607.png](./images/Pasted%20image%2020231220184607.png) 

## 3단계: 리포지토리 가져오기

패키지를 설치한 후 다음 단계는  [Visual Studio](https://ko.linux-console.net/?p=15010#) Code 리포지토리를 포함하는 것이지만 설치된 패키지를 인증하기 위해 Microsoft GPG 키를 가져와야 합니다.

```
$ wget -O- https://packages.microsoft.com/keys/microsoft.asc | sudo gpg --dearmor | sudo tee /usr/share/keyrings/vscode.gpg
```

![Pasted image 20231220184650.png](./images/Pasted%20image%2020231220184650.png)<br/>

이렇게 하면 설치된 패키지의 독창성을 확인할 수 있습니다. 이제  [Microsoft Visual](https://ko.linux-console.net/?p=15010#) Source 리포지토리를 포함하도록 이동하겠습니다.

```
$ echo deb [arch=amd64 signed-by=/usr/share/keyrings/vscode.gpg] https://packages.microsoft.com/repos/vscode stable main | sudo tee /etc/apt/sources.list.d/vscode.list
```

## 4단계: 시스템을 다시 업데이트합니다.

패키지를 설치하고 리포지토리를 가져온 후 운영 체제를 업데이트하는 것이 좋습니다.

```
$ sudo apt update
```

![Pasted image 20231220184734.png](./images/Pasted%20image%2020231220184734.png) 

시스템이 성공적으로 업데이트되었습니다.

## 5단계: 편집기 설치

이제  [Visual Studio](https://ko.linux-console.net/?p=15010#) Code Editor를 설치하기 위해 터미널에서 아래 주어진 명령을 실행하기만 하면 됩니다.

```
$ sudo apt install code
```

![Pasted image 20231220184833.png](./images/Pasted%20image%2020231220184833.png) 

 [Visual Studio](https://ko.linux-console.net/?p=15010#) 코드가 Ubuntu 22.04에 성공적으로 설치되었습니다.

## 앱 실행 방법

이 명령을 실행하여 애플리케이션을 시작하십시오.

```
$ code
```

**또는**

```
$ code &
```

이 외에도 Ubuntu에서 VS 코드를 시작하려면 애플리케이션 메뉴를 열고 코드를 검색합니다.

![Pasted image 20231220184917.png](./images/Pasted%20image%2020231220184917.png) 

이제 아이콘을 클릭하여 앱을 실행합니다.

![Pasted image 20231220184936.png](./images/Pasted%20image%2020231220184936.png)

이제 새 파일을 열고 코드 작성을 시작할 수 있습니다.

## Snap 스토어를 통해 Visual Studio Code 설치

Ubuntu의 Snap 스토어를 통해 Visual Studio 코드를 설치하려면 다음 명령을 실행하기만 하면 됩니다.

```
$ sudo snap install code
```

**출력**

![Pasted image 20231220185020.png](./images/Pasted%20image%2020231220185020.png)

편집기가 성공적으로 설치되었습니다.

Snap은 기본적으로 Ubuntu 22.04에 이미 설치되어 있습니다. 그러나 어떤 이유로 스냅이 없는 경우 아래 명령을 사용하여 설치할 수 있습니다.

```
$ sudo apt install snapd
```

![Pasted image 20231220185053.png](./images/Pasted%20image%2020231220185053.png)

## Ubuntu 22.04에서 Visual Studio 코드를 제거하는 방법

리포지토리와 키를 추가하여  [Visual Studio](https://ko.linux-console.net/?p=15010#) Code를 설치한 경우 아래에 입력한 명령을 사용하여 제거할 수 있습니다.

```
$ sudo apt remove code -y
```

![Pasted image 20231220185126.png](./images/Pasted%20image%2020231220185126.png)

스냅 저장소에서  [Visual Studio](https://ko.linux-console.net/?p=15010#) Code를 설치한 경우 아래 명령을 실행합니다.

```
$ sudo snap remove code --purge
```

![Pasted image 20231220185155.png](./images/Pasted%20image%2020231220185155.png)

편집기가 제거되었습니다.

## 결론

Ubuntu 22.04에 Visual Studio Code를 설치하려면 명령을 사용하여 특정 패키지를 설치한 다음 명령을 사용하여 Microsoft GPG 및 VS 리포지토리를 가져와야 합니다. 또한 이 앱은 스냅 스토어를 이용하여 설치할 수 있습니다. 이 자습서에서는 Ubuntu 22.04 LTS(Jammy Jellyfish)에서 Visual Studio Code를 설치, 시작 및 제거하는 방법에 대한 자세한 가이드를 제공합니다.
