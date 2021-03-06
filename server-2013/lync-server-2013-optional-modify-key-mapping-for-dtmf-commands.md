﻿---
title: 'Lync Server 2013: (선택 사항) DTMF 명령에 대한 키 매핑 수정'
TOCTitle: (선택 사항) DTMF 명령에 대한 키 매핑 수정
ms:assetid: d753b78d-400c-4df2-957f-e7576b2019c2
ms:mtpsurl: https://technet.microsoft.com/ko-kr/library/Gg398943(v=OCS.15)
ms:contentKeyID: 49305185
ms.date: 08/24/2015
mtps_version: v=OCS.15
ms.translationtype: HT
---

# (선택 사항) Lync Server 2013에서 DTMF 명령에 대한 키 매핑 수정

 

_**마지막으로 수정된 항목:** 2012-09-30_

전화 접속 회의 사용자는 전화기 키패드의 키를 눌러 DTMF(Dual-tone Multi-frequency) 명령을 수행할 수 있습니다. DTMF 명령을 사용하면 회의에 전화 접속한 사용자가 전화기의 키패드를 사용하여 음소거 설정 및 해제 또는 회의 잠금 설정 및 해제와 같은 회의 설정을 제어할 수 있습니다. cmdlet를 사용하여 DTMF 명령에 사용되는 키를 수정할 수 있습니다. 이 단계는 선택 사항입니다.


> [!NOTE]
> 이 cmdlet 및 지원되는 DTMF 옵션에 대한 자세한 내용은 Lync Server 관리 셸 설명서 또는 Lync Server 관리 셸 명령줄 도움말을 참조하십시오.



## DTMF 명령의 키 매핑을 수정하려면

1.  **RTCUniversalServerAdmins** 그룹의 구성원이나 **Cs-ServerAdministrator** 또는 **CsAdministrator** 역할의 구성원으로 컴퓨터에 로그온합니다.

2.  Lync Server 관리 셸 시작: **시작**, **모든 프로그램**, **Microsoft Lync Server 2013**을 차례로 클릭한 다음 **Lync Server 관리 셸**을 클릭합니다.

3.  명령 프롬프트에서 다음을 실행합니다.
    
        Get-CsDialinConferencingDtmfConfiguration
    
    이 cmdlet는 전화 접속 회의에 사용되는 DTMF 설정을 반환합니다.

4.  다음 cmdlet를 실행하고 변경할 각 옵션에 대해 누를 키를 지정합니다.
    
        Set-CsDialinConferencingDtmfConfiguration [-Identity <global or site collection to be changed>]
        [-AdmitAll <default key is 8>] [-AudienceMuteCommand <default key is 4>]
        [-CommandCharacter <* (default) | #>] [-EnableDisableAnnouncementsCommand <default key is 9>]
        [-HelpCommand <default key is 1>] [-LockUnlockConferenceCommand <default key is 7>]
        [-MuteUnmuteCommand <default key is 6>] [-PrivateRollCallCommand <default key is 3>]
    
    이 cmdlet는 전화 접속 회의에 사용되는 DTMF 설정을 수정합니다.
    
    예를 들면 다음과 같습니다.
    
        Set-CsDialinConferencingDtmfConfiguration -EnableDisableAnnouncementsCommand 4 -AudienceMuteCommand 9
    
    이 예에서는 알림을 사용하거나 사용하지 않도록 설정하기 위해 누르는 키와 모든 참가자에 대해 음소거를 설정 및 해제하기 위해 누르는 키를 바꿉니다. Identity가 지정되지 않았으므로 이 변경은 전역 DTMF 설정에 적용됩니다.

5.  (선택 사항) 특정 사이트에 대해 DTMF 명령 집합을 추가로 만들려면 사이트 ID와 함께 **New-CsDialinConferencingDtmfConfiguration** cmdlet를 사용합니다. 사이트에 대해 새 DTMF 설정을 만들면 이 사이트 설정이 전역 설정보다 우선합니다. 자세한 내용은 Lync Server 관리 셸 설명서나 Lync Server 관리 셸 명령줄 도움말을 참조하십시오.

