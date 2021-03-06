﻿---
title: 백업 및 복원 프로세스 개요
TOCTitle: 백업 및 복원 프로세스 개요
ms:assetid: e0f23b21-070f-4df5-b795-cea2f5338d85
ms:mtpsurl: https://technet.microsoft.com/ko-kr/library/Hh202192(v=OCS.15)
ms:contentKeyID: 52056972
ms.date: 08/24/2015
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 백업 및 복원 프로세스 개요

 

_**마지막으로 수정된 항목:** 2013-03-26_

이 섹션에서는 Lync Server 2013에 대해 백업 및 복원 프로세스가 작동되는 방식에 대한 개요를 제공합니다. 위치에 관계없이 모든 Standard Edition 서버 및 Enterprise Edition 서버에 대해 동일한 프로세스를 사용합니다.

일반적으로 백업 프로세스는 다음과 같이 작동합니다.

  - 특정 풀에 속하지 않는 독립 실행형 컴퓨터에서 공유 폴더로 백업 위치를 만듭니다. 백업 위치는 **$Backup**에서 참조됩니다.

  - 정기적인 예약을 통해 [Lync Server 백업](lync-server-2013-backing-up-lync-server.md)에 설명된 절차에 따라 [Lync Server 2013의 백업 및 복원 요구 사항: 데이터](lync-server-2013-backup-and-restoration-requirements-data.md)에서 설명하는 모든 Lync Server 데이터베이스 및 모든 파일 저장소를 백업합니다. 중앙 관리 저장소에는 모든 서버 설정 및 구성이 포함됩니다.

  - 이후 백업을 실행할 때마다 새 공유 폴더를 만들고 **$Backup**이 참조하는 경로를 변경합니다.

일반적으로 복원 프로세스는 다음과 같이 작동합니다.

  - 오류 또는 중단이 발생하면 **$Backup**에서 참조되는 위치의 데이터를 새 컴퓨터나 정상 상태의 컴퓨터에 복원합니다.
    

    > [!IMPORTANT]
    > 이 복원 프로세스에서는 데이터를 기존 서버 상태로 복원하지 않습니다. 즉, 이 프로세스에서는 서버가 신규 서버이거나 깨끗한 서버여야 합니다.



  - 사용자 및 회의 정보를 오류 지점까지 복구하려면 [Lync Server 2013의 고가용성 및 재해 복구 계획](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)에서 설명하는 것처럼 쌍으로 연결된 프런트 엔드 풀을 사용하여 재해 복구 토폴로지를 구현하면 됩니다. 이 옵션을 제외하면 Lync Server에서는 데이터베이스에 대해 단순 복구 모델만을 지원합니다. 단순 복구 모델에서는 데이터베이스가 마지막 전체 백업 지점까지 복구됩니다. 즉, 장애 지점이나 특정 시점까지 데이터베이스를 복원할 수는 없습니다. 대부분의 조직에서는 단순 복구 모델이 가장 적합한데, Lync Server 백 엔드 데이터베이스(RTCXDS.mdf)는 실제로 트랜잭션 로그 파일보다 작으며 일반적인 LOB(기간 업무) 데이터베이스 응용 프로그램의 데이터베이스보다도 훨씬 작기 때문입니다.

  - 모든 DNS(Domain Name System) 구성, DHCP(Dynamic Host Configuration Protocol) 구성, 도메인 이름, 컴퓨터 FQDN(정규화된 도메인 이름), 파일 저장소 경로 등은 백업할 때와 동일한 상태로 복원해야 합니다.

Lync Server 실행 서버에 오류가 발생할 경우 다음 단계가 복구에 포함됩니다.

  - 오류가 발생한 컴퓨터와 동일한 FQDN을 사용하여 신규 또는 깨끗한 컴퓨터에 운영 체제를 설치합니다.

  - 인증서를 다시 설치합니다.

  - 서버에서 데이터베이스를 호스트한 경우 Microsoft SQL Server 2012 또는 Microsoft SQL Server 2008 R2를 설치합니다.

  - 일반적으로 서버에 데이터베이스가 호스트된 경우 토폴로지 작성기를 실행하여 데이터베이스를 생성 및 설치하고 ACL(액세스 제어 목록)을 설정합니다.

  - 일반적으로는 서버에서 서버 역할을 호스트한 경우 Lync Server 배포 마법사의 1~4단계를 실행하여 로컬 구성 파일을 설치하고, 서버 역할 구성 요소를 설치하고, 인증서를 할당하고 서비스를 시작합니다.
    

    > [!NOTE]
    > 서버에서 서버 역할과 배치된 데이터베이스를 호스트한 경우 Lync Server 배포 마법사의 2단계를 실행하면 데이터베이스가 다시 만들어집니다.



  - 서버에서 데이터베이스를 호스트한 경우 백업된 데이터를 복원합니다.

