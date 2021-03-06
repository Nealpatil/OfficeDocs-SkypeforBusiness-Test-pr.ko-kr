﻿---
title: 'Lync Server 2013: 익명 사용자 지원을 위한 회의 정책 할당'
TOCTitle: 익명 사용자 지원을 위한 회의 정책 할당
ms:assetid: 662de022-1111-40f7-bad4-f2b686f30973
ms:mtpsurl: https://technet.microsoft.com/ko-kr/library/Gg521007(v=OCS.15)
ms:contentKeyID: 49303872
ms.date: 08/24/2015
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013에서 익명 사용자 지원을 위한 회의 정책 할당

 

_**마지막으로 수정된 항목:** 2012-10-19_

기본적으로 모든 사용자는 익명 사용자를 모임에 참여하도록 초대할 수 없습니다. 익명 사용자를 지원하도록 회의 정책을 구성하고 이 회의 정책을 특정 사용자에게 적용하여 익명 사용자를 초대할 수 있는 사용자를 제어합니다. 익명 사용자를 지원하도록 회의 정책을 구성하는 방법에 대한 자세한 내용은 [회의 정책 만들기 또는 수정](lync-server-2013-create-or-modify-a-conferencing-policy.md) 및 [Lync Server 2013에 대한 외부 액세스 및 페더레이션 관리](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md)를 참조하십시오.

이미 만든 회의 정책을 하나 이상의 사용자 또는 사용자 그룹에 적용하려면 이 섹션의 절차를 사용합니다.


> [!NOTE]
> 사용자가 익명 사용자를 초대할 수 있도록 정책을 구성하고 적용해야 할 뿐 아니라, 조직에서 익명 사용자를 지원하도록 설정해야 합니다. 자세한 내용은 <A href="lync-server-2013-configure-policies-to-control-public-user-access.md">Lync Server 2013에서 공용 사용자 액세스를 제어하도록 정책 구성</A>을 참조하십시오.



## 모임의 익명 참가에 대한 사용자 정책을 구성하려면

1.  RTCUniversalServerAdmins 그룹의 구성원(또는 이와 동일한 사용자 권한을 가진 사용자 계정) 또는 CsAdministrator 역할이 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.

2.  브라우저 창을 연 다음 Admin URL을 입력하여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작하는 데 사용할 수 있는 다양한 방법에 대한 자세한 내용은 [Lync Server 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조하세요.

3.  왼쪽 탐색 모음에서 **회의** 를 클릭하고 다음 중 하나를 수행합니다.
    
    1.  새 사용자 정책을 만들려면 **새로 만들기** 를 클릭하고 **사용자 정책** 을 클릭합니다. **이름** 필드에서 사용자 정책이 다루는 내용을 나타내는 고유한 이름을 만듭니다(예: 익명 사용자와 통신할 수 있도록 설정하는 사용자 정책의 경우 **EnableAnonymous** ).
    
    2.  기존 사용자 정책을 구성하려면 테이블에 나열되어 있는 적절한 정책을 클릭하고 **편집** , **세부 정보 표시** 를 차례로 클릭합니다.

4.  **회의 정책** 대화 상자에서 **참가자가 익명 사용자를 초대할 수 있도록 허용** 확인란을 선택합니다.

5.  **커밋** 을 클릭합니다.

6.  왼쪽 탐색 모음에서 **사용자** 를 클릭하고 구성할 사용자 계정을 검색합니다.

7.  검색 결과가 나열된 표에서 사용자 계정을 클릭하고 **편집** 을 클릭한 후에 **자세한 정보 표시** 를 클릭합니다.

8.  **Lync Server 사용자 편집** 의 **회의 정책** 에서 해당 사용자에게 적용할 익명 사용자 액세스 구성이 적용된 사용자 정책을 선택합니다.
    

    > [!NOTE]
    > <STRONG>&lt;자동&gt;</STRONG> 설정을 선택하면 기본 서버 설치 설정이 서버에 의해 자동으로 적용됩니다.



사용자가 회의에 익명 사용자를 초대할 수 있도록 하려면 조직에서 익명 사용자에 대한 지원을 사용하도록 설정해야 합니다. 자세한 내용은 배포 설명서 또는 작업 설명서에서 [Lync Server 2013에서 공용 사용자 액세스를 제어하도록 정책 구성](lync-server-2013-configure-policies-to-control-public-user-access.md)을 참조하십시오.

