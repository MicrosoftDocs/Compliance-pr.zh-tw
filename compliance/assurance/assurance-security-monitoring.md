---
title: 安全性監控概述
description: 深入瞭解 Microsoft 365 中的安全性監控
ms.author: robmazz
author: robmazz
manager: laurawi
ms.reviewer: sosstah
audience: Admin
ms.topic: article
f1.keywords:
- NOCSH
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
- MOE150
titleSuffix: Microsoft Service Assurance
ms.openlocfilehash: f3eae0aa5ba79372a7ce0d9a34d4dd35fe83a36b
ms.sourcegitcommit: 626b0076d133e588cd28598c149a7f272fc18bae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/30/2020
ms.locfileid: "49507283"
---
# <a name="security-monitoring-overview"></a>安全性監控概述

## <a name="what-is-microsofts-strategy-for-monitoring-security"></a>Microsoft 的監控安全性策略為何？

Microsoft 365 參與連續的安全性監視，以偵測和回應 Microsoft 365 服務的威脅。 安全監控和警示的主要原則包括：

- 健壯：偵測各種攻擊行為的信號和邏輯
- 準確性：有意義的提醒可避免干擾干擾
- 速度：能夠快速吸引攻擊者，以停止攻擊

「自動化」、「規模」和「雲端式解決方案」是我們監控和回應策略的重要重要項。 為了讓我們能夠以 Microsoft 365 核心服務的規模來有效地抓住及停止攻擊，我們的監控系統需要在近時間內自動提升非常精確的警示。 同樣地，當偵測到問題時，我們需要能夠以規模來緩解風險，我們無法依賴我們的團隊手動修正隨機器的問題。 為了降低風險規模，我們使用雲端式工具自動套用對策，並為工程師提供工具，以在整個環境中快速套用核准的緩解。

## <a name="how-does-microsoft-365-perform-security-monitoring"></a>Microsoft 365 如何執行安全性監控？

Microsoft 365 使用集中式記錄，針對可能指出安全性事件的活動，收集和分析記錄事件。 集中式記錄工具會從所有系統元件（包括事件記錄檔、應用程式記錄檔、存取控制記錄檔和網路型入侵偵測系統）匯總記錄。 除了伺服器記錄和應用層級資料之外，我們的服務中的核心基礎結構還配自自訂的安全代理程式，其會產生詳細遙測，並提供主機型入侵偵測。 我們使用此遙測進行監控和取證。

我們收集的記錄和遙測資料可啟用24/7 安全性警示。 我們的警示系統會在上傳記錄資料時進行分析，以接近即時產生警示。 這包括以機器學習模型為基礎的規則警示和更為複雜的警示。 我們的監控邏輯超出一般攻擊案例，並併入服務架構和作業的深入認知。 我們使用安全監控資料來不斷改進模型，以偵測新的攻擊種類，並改善安全性監控的準確性。

## <a name="how-does-microsoft-365-respond-to-security-monitoring-alerts"></a>Microsoft 365 如何回應安全監控警示？

當我們需要採取行動以回應提醒或進一步調查整個服務中的辨識證據時，我們的雲端式工具允許我們在整個環境中快速回應。 這些工具組括完全自動化的智慧代理程式，可回應偵測到的威脅與安全性對策。 在許多情況下，這些代理程式會部署自動對策，以在沒有人工干預的情況下，以規模緩解安全性偵測。 若無法做到這一點，安全性監控系統會自動提醒適當的通話工程師，其具備一組工具，讓他們能夠即時進行即時，以在規模範圍內緩解偵測到的威脅。 已升級至 Microsoft 365 安全性回應小組的潛在事件會透過安全性事件回應程式加以解決。

## <a name="how-does-microsoft-365-monitor-system-availability"></a>Microsoft 365 如何監控系統可用性？

Microsoft 365 主動監視其系統，以瞭解資源的使用狀況和反常使用方式。 資源監控是由服務冗余技術所結合，以協助避免意外停機，並讓客戶能夠可靠地存取產品和服務。 服務健康情況問題會透過服務健康情況儀表板 (SHD) ，立即向客戶傳遞。

## <a name="related-external-regulations--certifications"></a>相關的外部法規 & 認證

Microsoft 的線上服務會定期進行審核，以符合外部法規和認證。 請參閱下表，以驗證與安全性監控相關的控制項。

| **外部審計** | **Section** | **最新報告日期** |
|:--------|:--------|:------|
| [FedRAMP (Office 365) ](https://compliance.microsoft.com/compliancemanager) | AC-2：帳戶管理 <br> AC-17：遠端存取 <br> AU-7：審核減少與報告產生 <br> SI-4：資訊系統監控 <br> SI-7：軟體、固件和資訊完整性 <br> | 2020年9月24日 |
| [ISO 27001/27002 (Office 365) ](https://servicetrust.microsoft.com/ViewPage/MSComplianceGuideV3?command=Download&downloadType=Document&downloadId=d7864d4f-e053-4cc4-a964-fa526d07c3be&tab=7027ead0-3d6b-11e9-b9e1-290b1eb4cdeb&docTab=7027ead0-3d6b-11e9-b9e1-290b1eb4cdeb_ISO_Reports) <br> <br> [適用性聲明](https://servicetrust.microsoft.com/ViewPage/MSComplianceGuide?command=Download&downloadType=Document&downloadId=8ee1e46b-2ada-4e7b-bb7d-4c55a8cb6fcd&docTab=4ce99610-c9c0-11e7-8c2c-f908a777fa4d_ISO_Reports) <br> [認證](https://servicetrust.microsoft.com/ViewPage/MSComplianceGuideV3?command=Download&downloadType=Document&downloadId=70de0999-5451-43a3-9ef4-761e8fbfb1a3&tab=7027ead0-3d6b-11e9-b9e1-290b1eb4cdeb&docTab=7027ead0-3d6b-11e9-b9e1-290b1eb4cdeb_ISO_Reports) | 12.1.3：可用性監控與容量規劃 | 2020 年 2 月 22 日 |
| [ISO 27017 (Office 365) ](https://servicetrust.microsoft.com/ViewPage/MSComplianceGuideV3?command=Download&downloadType=Document&downloadId=d7864d4f-e053-4cc4-a964-fa526d07c3be&tab=7027ead0-3d6b-11e9-b9e1-290b1eb4cdeb&docTab=7027ead0-3d6b-11e9-b9e1-290b1eb4cdeb_ISO_Reports) <br><br> [適用性聲明](https://servicetrust.microsoft.com/ViewPage/MSComplianceGuide?command=Download&downloadType=Document&downloadId=8ee1e46b-2ada-4e7b-bb7d-4c55a8cb6fcd&docTab=4ce99610-c9c0-11e7-8c2c-f908a777fa4d_ISO_Reports) <br> [認證](https://servicetrust.microsoft.com/ViewPage/MSComplianceGuideV3?command=Download&downloadType=Document&downloadId=70de0999-5451-43a3-9ef4-761e8fbfb1a3&tab=7027ead0-3d6b-11e9-b9e1-290b1eb4cdeb&docTab=7027ead0-3d6b-11e9-b9e1-290b1eb4cdeb_ISO_Reports) | 12.1.3：可用性監控與容量規劃 <br> 16.1：管理資訊安全性事件和增強功能 | 2020 年 2 月 22 日 |
| [SOC 1 (Office 365) ](https://servicetrust.microsoft.com/ViewPage/MSComplianceGuideV3?command=Download&downloadType=Document&downloadId=b07c0f7b-6bd5-4544-8255-7a5f14bf914a&tab=7027ead0-3d6b-11e9-b9e1-290b1eb4cdeb&docTab=7027ead0-3d6b-11e9-b9e1-290b1eb4cdeb_SOC_/_SSAE_16_Reports) | CA-19：變更監控 <br> CA-26：安全性附隨報告 <br> CA-29：待命工程師 <br> CA-48：資料中心記錄 | 2019 年 9 月 30 日 |
| [SOC 2 (Office 365) ](https://servicetrust.microsoft.com/ViewPage/MSComplianceGuideV3?command=Download&downloadType=Document&downloadId=fa062990-e758-4ddc-ace3-7fb21a301d09&tab=7027ead0-3d6b-11e9-b9e1-290b1eb4cdeb&docTab=7027ead0-3d6b-11e9-b9e1-290b1eb4cdeb_SOC_/_SSAE_16_Rep-11e9-b9e1-290b1eb4cdeb_SOC_/_SSAE_16_Reports) | CA-19：變更監控 <br> CA-26：安全性附隨報告 <br> CA-29：待命工程師 <br> CA-30：可用性監控 <br> CA-48：資料中心記錄 | 2019 年 9 月 30 日 |
| [SOC 3 (Office 365) ](https://servicetrust.microsoft.com/ViewPage/MSComplianceGuideV3?command=Download&downloadType=Document&downloadId=9df8b99b-96ce-49a9-bff4-268031dcc9a6&tab=7027ead0-3d6b-11e9-b9e1-290b1eb4cdeb&docTab=7027ead0-3d6b-11e9-b9e1-290b1eb4cdeb_SOC_/_SSAE_16_Reports) | CUEC-08：報告事件 <br> CUEC-10：服務合約 | 2019 年 9 月 30 日 |

## <a name="resources"></a>資源

- [在幕後：保護 Microsoft 365 服務電源的基礎結構](https://download.microsoft.com/download/c/4/5/c45b197e-f0d9-4f40-bd5f-ed8fc7d0cd8c/M365DCSecurityIntro_Whitepaper.pdf)
