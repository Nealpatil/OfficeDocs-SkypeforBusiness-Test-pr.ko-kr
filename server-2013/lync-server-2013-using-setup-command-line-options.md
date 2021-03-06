﻿---
title: 설치 프로그램 명령줄 옵션 사용
TOCTitle: 설치 프로그램 명령줄 옵션 사용
ms:assetid: 99878c3c-ff31-48e2-8424-580d7b07a7bf
ms:mtpsurl: https://technet.microsoft.com/ko-kr/library/JJ205129(v=OCS.15)
ms:contentKeyID: 49304487
ms.date: 08/24/2015
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 설치 프로그램 명령줄 옵션 사용

 

_**마지막으로 수정된 항목:** 2015-03-09_

Setup.exe 명령줄이 사용되는 Office 설치 작업은 매우 한정적입니다. 제품 설치와 기능 사용자 지정에 설치 명령줄 옵션 대신 Office 사용자 지정 도구와 Config.xml 파일을 사용하는 것이 일반적입니다.

다음 표에는 Office Setup.exe 명령줄에서 인식하는 명령줄 옵션이 나와 있습니다.

### Office 설치 명령줄 옵션

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>설치 명령줄 옵션</th>
<th>설명</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>/admin</p></td>
<td><p>Office 사용자 지정 도구를 실행하여 설치 사용자 지정 파일(.msp 파일)을 만듭니다.</p></td>
</tr>
<tr class="even">
<td><p>/adminfile [path]</p></td>
<td><p>지정된 설치 사용자 지정 파일을 설치에 적용합니다. 특정 사용자 지정 파일(.msp 파일)의 경로 또는 사용자 지정 파일이 저장된 폴더의 경로를 지정할 수 있습니다.</p></td>
</tr>
<tr class="odd">
<td><p>/config [path]</p></td>
<td><p>설치하는 동안 설치 프로그램에서 사용할 Config.xml 파일을 지정합니다. 즉, /config 옵션을 사용하여 Lync 2013 설치를 위해 사용자 지정한 Config.xml 파일(예: <code>/config \\server\share\Lync15\Lync.WW\Config.xml</code>)을 지정합니다.</p></td>
</tr>
<tr class="even">
<td><p>/modify Lync</p></td>
<td><p>수정된 Config.xml 파일과 함께 유지 관리 모드로 설치 프로그램을 실행합니다. 예를 들어 /modify 옵션을 사용하여 Lync 기능을 추가하거나 제거할 수 있습니다.</p></td>
</tr>
<tr class="odd">
<td><p>/repair Lync</p></td>
<td><p>사용자 컴퓨터에서 설치 프로그램을 실행하여 Lync를 복구합니다.</p></td>
</tr>
<tr class="even">
<td><p>/uninstall Lync</p></td>
<td><p>설치 프로그램을 실행하여 사용자 컴퓨터에서 Lync를 제거합니다.</p></td>
</tr>
</tbody>
</table>


설치 명령줄 옵션 사용에 대한 자세한 내용은 [http://go.microsoft.com/fwlink/?linkid=267515\&clcid=0x412](http://go.microsoft.com/fwlink/?linkid=267515%26clcid=0x412)을 참조하십시오.

