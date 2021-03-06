﻿---
title: CDR 구성 설정 모음 만들기 또는 수정
TOCTitle: CDR 구성 설정 모음 만들기 또는 수정
ms:assetid: c830be5a-2a82-468d-9c46-d3fec0f79fd0
ms:mtpsurl: https://technet.microsoft.com/ko-kr/library/JJ721878(v=OCS.15)
ms:contentKeyID: 49885977
ms.date: 08/24/2015
mtps_version: v=OCS.15
ms.translationtype: HT
---

# CDR 구성 설정 모음 만들기 또는 수정

 

_**마지막으로 수정된 항목:** 2015-03-09_

CDR(통화 정보 기록)을 사용하면 피어 투 피어 메신저 대화 세션, VoIP(Voice over Internet Protocol) 전화 통화, 전화 회의 통화 등의 사용 현황을 추적할 수 있습니다. 이러한 사용 내역 데이터에는 누가 누구에게 전화를 걸었는지, 언제 전화를 걸었는지 및 얼마나 오래 통화했는지에 대한 정보가 포함됩니다.

Microsoft Lync Server 2013을 설치하면 CDR 구성 설정의 전체 컬렉션이 하나 만들어집니다. 관리자에게는 또한 사이트 범위에서 사용자 지정 설정을 만드는 옵션이 제공됩니다. 이러한 사이트 범위의 설정은 사용될 때마다 전역 설정보다 높은 우선 순위를 갖습니다. 예를 들어 레드몬드 사이트에 사이트 범위의 설정을 만들면 전역 설정이 아닌 해당 설정이 레드몬드의 CDR 관리에 사용됩니다.

Lync Server 제어판 또는 [New-CsCdrConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsCdrConfiguration) cmdlet 중 하나를 사용하여 CDR 구성 설정을 만들 수 있습니다. Lync Server 제어판 또는 [Set-CsCdrConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsCdrConfiguration) cmdlet을 사용하여 기존 설정을 수정할 수 있습니다. Lync Server 제어판을 사용하여 설정을 만들고 수정하는 경우 다음 옵션을 사용할 수 있습니다.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>UI 설정</th>
<th>PowerShell 매개 변수</th>
<th>설명</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>이름</p></td>
<td><p>Identity</p></td>
<td><p>CDR 구성 설정에 대한 고유 ID가 만들어집니다. 이러한 설정은 사이트 범위에서만 만들 수 있습니다.</p></td>
</tr>
<tr class="even">
<td><p>CDR 모니터링 사용</p></td>
<td><p>EnableCDR</p></td>
<td><p>CDR을 사용할 수 있는지 여부를 나타냅니다.</p></td>
</tr>
<tr class="odd">
<td><p>CDR 삭제 사용</p></td>
<td><p>EnablePurging</p></td>
<td><p>CDR을 CDR 데이터베이스에서 주기적으로 삭제할지 여부를 나타냅니다.</p></td>
</tr>
<tr class="even">
<td><p>최대 기간(일) 동안 CDR 유지</p></td>
<td><p>KeepCallDetailForDays</p></td>
<td><p>CDR 기록을 CDR 데이터베이스에 유지할 일 수를 나타냅니다. 지정된 일 수보다 오래된 기록은 모두 자동으로 삭제됩니다. 삭제는 삭제를 사용하도록 설정한 경우에만 수행됩니다.</p></td>
</tr>
<tr class="odd">
<td><p>최대 기간(일) 동안 오류 보고서 데이터 유지</p></td>
<td><p>KeepErrorReportForDays</p></td>
<td><p>CDR 오류 보고서를 유지할 일 수를 나타냅니다. 지정된 일 수보다 오래된 보고서는 모두 자동으로 삭제됩니다. CDR 오류 보고서는 클라이언트 응용 프로그램에서 업로드하는 진단 보고서입니다.</p></td>
</tr>
</tbody>
</table>



> [!NOTE]
> New-CsCdrConfiguration 및 Set-CsCdrConfiguration cmdlet에 포함된 추가 옵션 중에는 Lync Server 제어판에서 사용할 수 없는 것이 있습니다. 자세한 내용은 <A href="https://docs.microsoft.com/en-us/powershell/module/skype/New-CsCdrConfiguration">New-CsCdrConfiguration</A> 및 <A href="https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsCdrConfiguration">Set-CsCdrConfiguration</A> 도움말 항목을 참조하십시오.



## Lync Server 제어판을 사용하여 CDR 구성 설정을 만들려면

1.  Lync Server 제어판에서 **모니터링 및 보관**을 클릭합니다.

2.  **통화 정보 기록** 탭에서 **새로 만들기**를 클릭합니다.

3.  **사이트 선택** 대화 상자에서 새 구성 설정을 만들 사이트를 선택합니다. 대화 상자가 빈 상태이면 이미 사이트가 모두 CDR 구성 설정 컬렉션에 할당되었다는 의미입니다. 각 사이트는 단일 CDR 컬렉션으로 제한됩니다. 따라서 설정을 삭제한 후 다시 만들거나, 간단히 기존 설정을 수정하면 됩니다.

4.  **새 통화 정보 기록 설정 만들기** 대화 상자에서 원하는 항목을 선택한 다음 **커밋**을 클릭합니다.

## Lync Server 제어판을 사용하여 기존 CDR 구성 설정을 수정하려면

1.  Lync Server 제어판에서 **모니터링 및 보관**을 클릭합니다.

2.  수정할 설정 컬렉션을 두 번 클릭하거나 컬렉션을 선택하고 **편집**을 클릭한 다음 **자세한 정보 표시**를 클릭합니다. 한 번에 한 컬렉션만 수정할 수 있습니다. 다른 컬렉션도 동일하게 변경하려면 Lync Server 관리 셸을 대신 사용합니다.

3.  **통화 정보 기록 설정 편집** 대화 상자에서 원하는 항목을 선택한 다음 **커밋**을 클릭합니다.

## Lync Server 관리 셸 cmdlet을 사용하여 CDR 구성 설정을 만들려면

CDR 구성 설정을 Windows PowerShell 및 **New-CsCdrConfiguration** cmdlet을 사용하여 만들 수도 있습니다. 이 cmdlet은 Lync Server 2013 관리 셸 또는 원격 세션의 Windows PowerShell에서 실행할 수 있습니다. 원격 Windows PowerShell을 사용하여 Lync Server에 연결하는 방법에 대한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서인 "빠른 시작: 원격 PowerShell을 사용하여 Microsoft Lync Server 2010 관리"([http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876))를 참조하세요.

## 새 CDR 구성 설정 컬렉션을 만들려면

  - 다음 명령을 실행하면 레드몬드 사이트에 적용되는 새 CDR 구성 설정을 만들 수 있습니다.
    
        New-CsCdrConfiguration -Identity "site:Redmond"

## CDR(통화 정보 기록)을 사용하지 않도록 설정하는 CDR 구성 설정 컬렉션을 만들려면

  - 이전 명령에서 필수 Identity 매개 변수를 제외하고는 지정된 매개 변수가 없으므로 새 구성 설정 컬렉션에는 모든 속성의 기본값이 사용됩니다. 다른 속성 값을 사용하는 설정을 만들려면 간단히 적합한 매개 변수와 매개 변수 값을 포함하면 됩니다. 예를 들어 CDR(통화 정보 기록)을 기본적으로 사용하지 않도록 설정하는 CDR 구성 설정 컬렉션을 만들려면 다음과 같은 명령을 실행하면 됩니다.
    
        New-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False

## 새 CDR 구성 설정 컬렉션을 만들 때 여러 속성 값을 지정하려면

  - 여러 매개 변수를 포함하여 여러 속성 값을 수정할 수 있습니다. 예를 들어 다음 명령을 실행하면 CDR(통화 정보 기록)을 30일 동안, 오류 보고서를 90일 동안 보관하는 새 설정을 구성할 수 있습니다.
    
        New-CsCdrConfiguration -Identity "site:Redmond" -KeepCallDetailForDays 30 -KeepErrorReportForDays 90

자세한 내용은 [New-CsCdrConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsCdrConfiguration) cmdlet에 대한 도움말 항목을 참조하십시오.

