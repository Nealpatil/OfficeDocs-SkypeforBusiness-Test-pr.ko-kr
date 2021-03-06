﻿---
title: 'Lync Server 2013: tblComplianceData'
TOCTitle: tblComplianceData
ms:assetid: 05b28f9b-4aba-4b69-ba8d-2ceeb6cbfaac
ms:mtpsurl: https://technet.microsoft.com/ko-kr/library/Gg558606(v=OCS.15)
ms:contentKeyID: 49302680
ms.date: 08/10/2015
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013의 tblComplianceData

 

_**마지막으로 수정된 항목:** 2015-03-09_

tblComplianceData에는 준수 어댑터에서 아직 처리되지 않은 준수 이벤트가 포함됩니다.

### 열

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>열</th>
<th>유형</th>
<th>설명</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>cmplEventID</p></td>
<td><p>bigint, null이 아님</p></td>
<td><p>이벤트 ID입니다.</p></td>
</tr>
<tr class="even">
<td><p>entryDate</p></td>
<td><p>smalldatetime, null이 아님</p></td>
<td><p>삽입 시간(cmplType=9의 경우에는 항목이 단순히 자리 표시자이므로 오랜 시간 후일 수 있음)</p></td>
</tr>
<tr class="odd">
<td><p>cmplType</p></td>
<td><p>int, null이 아님</p></td>
<td><p>준수 이벤트 유형:</p>
<ul>
<li><p>1: 채팅</p></li>
<li><p>2: 백채트</p></li>
<li><p>3: 파일 다운로드</p></li>
<li><p>4: 파일 업로드</p></li>
<li><p>9: 임시 파일 전송</p></li>
<li><p>10: 채팅 삭제(바꾸기 포함)</p></li>
<li><p>11: 채팅 삭제</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>cmplTime</p></td>
<td><p>bigint, null이 아님</p></td>
<td><p>이벤트의 타임스탬프입니다.</p></td>
</tr>
<tr class="odd">
<td><p>cmplChannelUri</p></td>
<td><p>nvarchar(255), null이 아님</p></td>
<td><p>채널 URI(Uniform Resource Identifier)입니다.</p></td>
</tr>
<tr class="even">
<td><p>cmplChatID</p></td>
<td><p>bigint</p></td>
<td><p>채팅 ID(tblChat.chatId 테이블에 해당됨)</p></td>
</tr>
<tr class="odd">
<td><p>cmplUserID</p></td>
<td><p>int, null이 아님</p></td>
<td><p>게시자의 사용자 ID(tblPrincipal.prinID 테이블에 해당됨)</p></td>
</tr>
<tr class="even">
<td><p>cmplUserUri</p></td>
<td><p>nvarchar(255), null이 아님</p></td>
<td><p>사용자 URI입니다.</p></td>
</tr>
<tr class="odd">
<td><p>cmplMessage</p></td>
<td><p>nvarchar(max)</p></td>
<td><p>메시지(인코딩은 cmplType에 따라 다름)</p></td>
</tr>
</tbody>
</table>


### 키

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>열</th>
<th>설명</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>cmplEventID</p></td>
<td><p>기본 키입니다.</p></td>
</tr>
</tbody>
</table>

