# Tkinter Designer 사용법

___

## 목차

1. [**시작하기**](#getting-started-1)
   1. [Python 설치하기](#getting-started-1)
   2. [Tkinter Designer 설치하기](#getting-started-2)
   3. [Figma 계정 생성하기](#getting-started-3)

2. [**Figma 가이드**](#formatting-1)
   1. [레퍼런스](#formatting-1)
   2. [속성 가이드](#formatting-2)

3. [**Tkinter Designer 사용하기**](#Using-Tkinter-Designer)
   1. [Access Token](#using-1)
   2. [File URL 가져오기](#using-2)
   3. [CLI 사용하기](#using-cli)
   4. [GUI 사용하기](#using-gui)

4. [**문제해결**](#Troubleshooting)

<br><br>

# 시작하기 <small>[[Top](#table-of-contents)]</small>

<a id="getting-started-1"></a>

## 1. Python 설치하기

Tkinter Designer를 사용하기 전에 Python을 설치해야 합니다.  
- [여기에서 Python을 설치할 수 있습니다.](https://www.python.org/downloads)  
- [다음은 다양한 운영 체제에 Python을 설치하는 데 유용한 가이드입니다.](https://wiki.python.org/moin/BeginnersGuide/Download)

*이 가이드의 뒷부분에서 Python용 Package Installer(pip)를 사용할 것이며, 이 경우 시스템 환경변수에 Python을 추가해야 할 수도 있습니다.*

___
<br>

<a id="getting-started-2"></a>

## 2. Tkinter Designer 설치하기

*세 가지 옵션:*

1. `pip install tkdesigner`

2. [poetry](https:python-poetry.org) 설치
   - `poetry new <gui_project_name> && cd <gui_project_name>`
   - `poetry add tkdesigner`
   - `poetry install`

3. 소스 코드에서 Tkinter Designer를 실행하려면 아래 지침을 따르십시오.

   1. Tkinter Designer의 원본 파일을 수동으로 다운로드하거나 GIT를 사용하여 다운로드합니다.

      ` git clone https://github.com/ParthJadhav/Tkinter-Designer.git `

   2. 작업 디렉토리를 Tkinter Designer로 변경합니다.

      `cd Tkinter-Designer`

   3. 다음을 실행하여 필요한 종속성을 설치합니다.

      - `pip install -r requirements.txt`
         - pip이 작동하지 않는 경우 다음 명령도 사용해 보십시오:
         - `pip3 install -r requirements.txt`
         - `python -m pip install -r requirements.txt`
         - `python3 -m pip install -r requirements.txt`
         - 그래도 작동하지 않으면 환경변수에 Python이 추가되었는지 확인합니다.

   그러면 모든 요구 사항과 Tkinter Designer가 설치됩니다. Tkinter Designer를 사용하기 전에 아래 지침을 사용하여 Figma 파일을 만들어야 합니다.

   파일을 이미 만든 경우 [**TkinterDesigner 사용하기**](#Using-Tkinter-Designer) 섹션으로 건너뜁니다.

___
<br>

<a id="getting-started-3"></a>

## 3. Figma 계정 생성하기

1. 웹 브라우저에서 [figma.com ](https://www.figma.com/) )로 이동하여 '가입'을 클릭합니다.
2. 정보를 입력한 다음 이메일 인증을 합니다.
3. 새로운 Figma 파일을 만듭니다.
4. GUI 제작 시작
   - 다음 섹션에서는 Tkinter Designer 입력에 필요한 형식에 대해 설명합니다.
     - [초보자를 위한 공식 피그마 튜토리얼 시리즈입니다.](https://www.youtube.com/watch?v=Cx2dkpBxst8&list=PLXDU_eVOJTx7QHLShNqIXL1Cgbxj7HlN4)
     - [피그마 공식 유튜브 채널입니다.](https://www.youtube.com/c/Figmadesign/featured)
     - [여기가 피그마 도움말입니다.](https://help.figma.com/hc/en-us)

<br><br>

<a id="formatting-1"></a>

# Figma 가이드 <small>[[Top](#table-of-contents)]</small>

## 1. 레퍼런스

<br>

### Naming이 중요합니다

| Figma Element Name | Tkinter Element |
| --- | --- |
| Button | Button |
| Line | Line |
| Text | Name it anything |
| Rectangle | Rectangle |
| TextArea | Text Area |
| TextBox | Entry |
| Image | Canvas.Image() |

<br>

Tkinter Designer에서 생성된 코드는 Figma 설계의 요소 이름을 기반으로 하므로 요소 이름을 적절하게 지정해야 합니다. 피그마의 레이어 패널에서 요소를 두 번 클릭하여 이름을 바꿉니다.

___
<br>

<a id="formatting-2"></a>

## 2. 속성 가이드

<br>

1. **먼저 Tkinter 창 역할을 할 프레임을 만듭니다.**
<br><br>

2. **Image**
   - 도형 및/또는 이미지를 사용하여 이미지를 생성할 수 있습니다.
   - 여러 도형/이미지를 사용하는 경우 '모두 선택'을 눌러 그룹화해야 합니다 <kbd>CTRL/&#8984; + G</kbd>
   - 그런 다음 요소 또는 그룹의 이름을 "이미지"로 지정합니다.
<br><br>

3. **Text (일반 텍스트)**
   - <kbd>T</kbd> 키를 눌러 텍스트 도구를 활성화한 다음 원하는 대로 텍스트 추가합니다.
   - Tkinter Designer에서 사용하기 위해 텍스트 이름을 변경할 필요가 없습니다.
   - 명시적으로 <kbd>Return</kbd> 또는 <kbd>Enter</kbd> 키를 눌러 다음 줄로 이동합니다.
<br><br>

4. **Entry (Single-Line User Input)**
   - Activate the Rectangle tool with <kbd>R</kbd>
   - Adjust the Rectangle to your liking
   - Make sure the Rectangle is named "TextBox"
<br><br>

5. **Text Area (Multi-Line User Input)**
   - Activate the Rectangle tool with <kbd>R</kbd>
   - Adjust the Rectangle to your liking
   - Make sure the Rectangle is named "TextArea"

6. **Rectangle**
   - Activate the Rectangle tool with <kbd>R</kbd>
   - Adjust the Rectangle to your liking
   - Make sure the Rectangle is named "Rectangle"
<br><br>

7. **Normal Button**
   - Add rectangle to serve as a button in your GUI
     - Optional: Add text for the button
   - Select the button(Rectangle), and any optional text, then group them with <kbd>CTRL/&#8984; + G</kbd>
   - Name the group "Button"

#### Refer to [this video](https://youtu.be/Qd-jJjduWeQ) if you face any problem

<br><br>

8. **Rounded Button**
   - Add rectangle to serve as a button in your GUI
     - Optional: Add text for the button
   - Make it rounded by adding corner radius by selecting the rectangle and adding corner radius from the right side. [Read more on it](https://help.figma.com/hc/en-us/articles/360050986854-Adjust-corner-radius-and-smoothing)
   - Create a Rectangle with same size of your button. Don't make it rounded.
   - Change the Rectangle's color to match the Background
   - Now move the newly created rectangle below the main button(Rectangle).
   - Select the button, Rectangle, and any optional text, then group them with <kbd>CTRL/&#8984; + G</kbd>
   - Name the group "Button"

#### Refer to [this video](https://youtu.be/Qd-jJjduWeQ) if you face any problem

<br><br>

<a id="Using-Tkinter-Designer"></a>

# Using Tkinter Designer <small>[[Top](#table-of-contents)]</small>

## Required Inputs

There are some inputs you'll need to collect to be able to use the TKinter Designer.

<a id="using-1"></a>

### 1. Personal Access Token

1. Log into your Figma account
2. Navigate to Settings
3. In the **Account** tab, scroll down to **Personal access tokens**
4. Enter the name of your access token in the entry form and press <kbd>Enter</kbd>
5. Your personal access token will be created.
   - Copy this token and keep it somewhere safe.
   - **You will not get another chance to copy this token.**

<a id="using-2"></a>

### 2. Getting your File URL

1. In your Figma design file, click the **Share** button in the top bar, then click on **&#x1f517; Copy link**

<a id="using-cli"></a>

## Using the CLI

Using the CLI is as simple as installing the package and running the CLI tool.

### From PyPi

You can use the below command as test by replacing $FILE_URL & $FIGMA_TOKEN by your data. If you haven't got the token and link then refer to [**Required Inputs Section**](#using-1).

``` bash
pip install tkdesigner

tkdesigner $FILE_URL $FIGMA_TOKEN
```

### From Source

To use CLI from the source code you need to clone the repository and then follow the below instructions.

You can use the below command as test by replacing $FILE_URL & $FIGMA_TOKEN by your data. If you haven't got the token and link then refer to [**Required Inputs Section**](#using-1).

```bash
$ python -m tkdesigner.cli $FILE_URL $FIGMA_TOKEN

# To learn more about how to use the cli, pass the --help flag
$ python -m tkdesigner --help
```

### Output

By default, the GUI code will be written to build/gui.py. You can specify the output path by using `-o` Flag and providing the path.

To run the generated GUI, cd into the directory you built it to (e.g. build/) and run it just as you would any Tkinter GUI.

```bash
cd build
python3 gui.py
```

<a id="using-gui"></a>

## Using the GUI

### Open Tkinter Designer before doing the following steps

<br>

1. Open TKinter Designer GUI by

```
cd Tkinter-Designer
cd gui
python3 gui.py
```

2. Paste your *personal access token* into the **Token ID** form in Tkinter Designer
3. Paste the link into the **File URL** form in Tkinter Designer
4. Click the **Output Path** form to open a file browser
5. Choose an output path and click **Select Folder**
6. Press **Generate**

The output files from Tkinter Designer will be placed in your chosen directory, inside a new folder called **build**. Congratulations, you have now created your Tkinter GUI using Tkinter Designer!

<br><br>

<a id="Troubleshooting"></a>

# Troubleshooting <small>[[Top](#table-of-contents)]</small>

- Elements not visible? Misplaced?
  - Please make sure that your Figma File has its elements named correctly. * See [Formatting Your Figma Design, &sect;1](#formatting-1)

- Button has an unintended gray background?
  - Make sure you have added a Rectangle behind your button element, and that its Fill color is the same as the Background's

- Incorrect elements?
  - Make sure you have named your elements correctly in Figma
    - See [Formatting Your Figma Design, &sect;1](#formatting-1)

- Window is larger than the screen?
  - Reduce the size of your elements in Figma

- Files not generating?
  - Restart Tkinter Designer
  - Double-check the token and URL
  - Make sure your design has a Frame

- Something else?
  - [Report issues not listed here on GitHub](https://github.com/ParthJadhav/Tkinter-Designer/issues/new)
