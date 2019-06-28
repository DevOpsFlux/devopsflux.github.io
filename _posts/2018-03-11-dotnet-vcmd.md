---
layout: post
title: "DotNet 주석 템플릿 매크로 설정 Visual Commander"
subtitle:   "DotNet Visual Commander Tools 활용"
date: 2018-03-11 20:00:00 -0400
categories: tip
tags: tools
---


## .NET 주석 매크로 사용

### Visual Commander Macro
- 설치 : [https://marketplace.visualstudio.com/items?itemName=SergeyVlasov.VisualCommander](https://marketplace.visualstudio.com/items?itemName=SergeyVlasov.VisualCommander){:target="_blank"}
1. VCmd > Command 생성 : idoc 
'''
Sub Run(DTE As EnvDTE80.DTE2, package As Microsoft.VisualStudio.Shell.Package) Implements VisualCommanderExt.ICommand.Run

	Dim textSelection As EnvDTE.TextSelection
	textSelection = DTE.ActiveWindow.Selection
	textSelection.Insert("/// <summary>API 명칭</summary>")
	textSelection.NewLine()
	textSelection.Insert("<remarks>API 상세 설명</remarks>")
	textSelection.NewLine()
	textSelection.Insert("<methods>POST</methods>")
	textSelection.NewLine()
	textSelection.Insert("<displays>3,7,10</displays>")
	textSelection.NewLine()
	textSelection.Insert("<updates>2019-06-21 18:59:59</updates>")
	textSelection.NewLine()
	textSelection.Insert("<param name=""vFlag"" type=""varcahr"" length=""1"" required=""Y"" iskey="""">구분자</param>")
	textSelection.NewLine()
	textSelection.Insert("<request></request>")
	textSelection.NewLine()
	textSelection.Insert("<response></response>")

End Sub
'''

![img1](/assets/img/post/dotnet/img1.jpg)

2. 도구 > 옵션 > 키보드
- Ctrl + / 로 키 매핑 및 실행

![img2](/assets/img/post/dotnet/img2.jpg)

![img3](/assets/img/post/dotnet/img3.jpg)


