---
layout: single
title: python 가상환경 설정 (conda없이)
categories: deeplearing
lang: ko
subtitle: pip없이 파이썬 가상환경 설정 in windows10 with VScode
tags: [pip, python, cuda, cudnn, gpu, windows, tensorflow, VScode]
comments: true
---

This is a post to make virtual environment to build python code.

[Referring Website](https://theorydb.github.io/dev/2020/02/14/dev-dl-setting-local-python/)
참고 사이트는 Conda를 이용해서 가상환경을 설치했지만,

저는 **Conda를 사용하지 않고 가상환경을 설치합니다.**

제가 다니는 회사 보안 방침 상 Conda를 설치하면 당장 삭제하라는 경고 알람이 뜨기 때문에... 없는 버전으로 환경을 만들게 되었습니다.

혹시나 저와 같은 문제를 겪으시는 분들을 위해 이 포스팅을 작성하게 되었습니다.


## 내가 구축할 스택:

| 환경 | 버전 |
| :------ |:--- |
| Windows | 10 64-bit |
| Python | 3.7 |
| TensorFlow GPU | 2.3 |



<H1> 1.Gpu driver 및 cuda & cudnn설치 </H1>

## Windows 버전 확인

내pc -> 마우스 우클릭 -> 속성
{: .box-note}
<center>
  <img
    src="/assets/images/virtualenv/1.png"
  />
</center>


## GPU확인 및 설치 권장 GPU Driver확인

내 PC에 장착된 GPU 모델 확인

[윈도우키+X] -> 장치관리자 -> 디스플레이 어댑터 -> 모델명 확인

<center>
  <img
    src="/assets/images/virtualenv/2.png"
  />
</center>

## GPU driver 추천 확인

작업표시줄 돋보기 클릭 -> cmd 검색 -> "nvidia-smi" 입력 -> driver version 확인

*이 Driver는 컴에 깔린 driver 가 아님. 권장 Driver임!!

<center>
  <img
    src="/assets/images/virtualenv/3.png"
  />
</center>


## GPU Compute Capability확인

[cuda-gpus](https://developer.nvidia.com/cuda-gpus)에 들어가서 본인 GPU에 맞는 Compute Capability 확인 (작성자는 6.1)

<center>
  <img
    src="/assets/images/virtualenv/4.png"
  />
</center>


## CUDA SDK확인

[위키-CUDA](https://en.wikipedia.org/wiki/CUDA)에 들어가서 Compute Capability에 맞는 CUDA SDK 버전 확인 (작성자는 11.x)

<center>
  <img
    src="/assets/images/virtualenv/5.png"
  />
</center>


## CUDA Toolkit 설치

[cuda-toolkit-archive](https://developer.nvidia.com/cuda-toolkit-archive)에 들어가서 CUDA Toolkit 다운로드 및 설치(작성자는 11.3.0설치)

*로그인 필요

*설치 과정에서 SDK 오류로 CUDA 설치가 안되면 "제어판>프로그램 추가/제거"에서 "nvidia frameview sdk"삭제하고 다시 cuda설치하면 됨.

<center>
  <img
    src="/assets/images/virtualenv/6.png"
  />
</center>


## CUDA SDK확인

[여기](https://en.wikipedia.org/wiki/CUDA)에 들어가서 Compute Capability에 맞는 CUDA SDK 버전 확인 (작성자는 11.x)

<center>
  <img
    src="/assets/images/virtualenv/5.png"
  />
</center>


Here's a code chunk:

~~~
var foo = function(x) {
  return(x + 5);
}
foo(3)
~~~

And here is the same code with syntax highlighting:

```javascript
var foo = function(x) {
  return(x + 5);
}
foo(3)
```

And here is the same code yet again but with line numbers:

{% highlight javascript linenos %}
var foo = function(x) {
  return(x + 5);
}
foo(3)
{% endhighlight %}

## Boxes
You can add notification, warning and error boxes like this:

### Notification

{: .box-note}
**Note:** This is a notification box.

### Warning

{: .box-warning}
**Warning:** This is a warning box.

### Error

{: .box-error}
**Error:** This is an error box.
