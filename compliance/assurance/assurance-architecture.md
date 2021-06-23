---
title: 架構概觀
description: 深入瞭解 Microsoft 365 中的架構
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
- MS-Compliance
search.appverid:
- MET150
- MOE150
titleSuffix: Microsoft Service Assurance
hideEdit: true
ms.openlocfilehash: 9af5296cce34db6362638f025f38315f2e1d7b05
ms.sourcegitcommit: fb379d1110a9a86c7f9bab8c484dc3f4b3dfd6f0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/23/2021
ms.locfileid: "53088532"
---
# <a name="architecture-overview"></a>架構概觀

## <a name="what-is-microsoft-365"></a>什麼是 Microsoft 365？

Microsoft 365 是雲端電源、訂閱 Office、Windows 10、Enterprise Mobility + Security 及規範的版本。 Microsoft 365 客戶取得 Outlook 和 Windows 之類的用戶端，也會受益于 Microsoft 裝載的服務，例如 Exchange Online、Microsoft Teams 和 SharePoint 線上。 服務的所有元件都會定期更新為訂閱模式的一部分，讓我們的客戶擁有「長綠」的產品。 Microsoft 會代表客戶管理服務基礎結構，這表示 Microsoft 負責保護儲存客戶資料的基礎結構。

根據規模的角度，我們目前使用近百萬台電腦來 Microsoft 365 服務。 針對這些服務的基礎結構，在 Azure、Windows 和 Linux 以及多承租人和專用平臺的服務特定硬體和虛擬化環境上有很大的差異。 Microsoft 365 是一種全域業務，而且我們的基礎結構是遍佈世界各地的資料中心，讓我們的客戶能夠滿足資料派駐和主權需求。

簡而言之，此服務很複雜，以驚人的規模執行，需要成千上萬的 Microsoft 工程師才能建立及維護。 我們將所有這種基礎結構保持在最安全的頭等大事。

## <a name="how-does-microsoft-365-ensure-isolation-between-customer-tenants"></a>Microsoft 365 如何確保客戶承租人之間的隔離？

Microsoft 的雲端服務是以假設所有租使用者可能會敵意所有其他租使用者所組成。 為了正確地將承租人彼此隔離，Microsoft 會執行各種隔離技術和控制措施。 這些控制項的設計目的是為了避免資訊洩露或未經授權存取跨承租人的客戶資料，並防止一個承租人的動作對其他租使用者的服務造成不良影響。

使用 Azure Active Directory (Azure AD) ，在 Microsoft 365 承租人內邏輯隔離客戶內容。 在 Microsoft 365 中的使用者驗證不僅會驗證使用者身分識別，還會驗證使用者帳戶所屬的承租人身分識別，以防止使用者存取其租使用者環境以外的資料。 若要對 Azure AD 的邏輯隔離進行補充，客戶內容會永遠在靜止時加密，並可在傳輸中加密。 個別服務也可能會提供額外的租使用者隔離層，例如在個別的加密資料庫中 SharePoint 線上隔離租使用者資料。

## <a name="how-does-microsoft-365-engineer-resilient-services-that-avoid-single-points-of-failure"></a>如何 Microsoft 365 工程師的彈性服務以避免單一失敗點？

Microsoft 設計並組建雲端服務，以最大限度地提升可靠性，並將對客戶面臨的負面影響降至最低，以應對一般作業的錯誤和挑戰。 此策略的開始是連接地理位置分散的資料中心網路的網路設計。 Microsoft 的網路架構包括直接互連和多個網路路徑。 Microsoft 365 服務會利用此冗余，自動路由傳送失敗的流量，以提升服務品質。

在服務層級，Microsoft 365 的修復原則會將軟體恢復優先順序。 在任何情況下，我們的服務都會以自動化服務狀況監視方式部署在主動/主動設定中，允許服務偵測和復原許多常見的錯誤和失敗，而不需要人工干預。 除了主動/主動設定之外，Microsoft 365 服務可確保服務部署在不同的容錯區域中，避免某個區域中的錯誤影響其他區域的可用性。

資料恢復可保護 Microsoft 365 服務中的資料完整性及可用性，以補充服務恢復性。 我們的服務使用本機儲存裝置冗余和地域冗余，將客戶資料的複本複寫到不同的容錯區域。 如果一個容錯區域中的資料損毀或遺失，可在另一個容錯區域中存取，而不會失去可用性。 自動完整性檢查會自動還原由許多實體或邏輯損毀所影響的資料。 Microsoft 365 也為客戶提供工具，以在 Exchange Online 和 SharePoint 線上時，還原客戶意外刪除或修改的資料。

## <a name="how-does-microsoft-365-track-dependencies-and-prevent-unauthorized-external-system-connections"></a>Microsoft 365 如何追蹤相依性，以及如何防止未經授權的外部系統連線？

Microsoft 365 服務小組會識別重要的系統元件及其相依性，以作為商務持續性管理的一部分。 此外，Microsoft 365 檔和追蹤所有外部系統連線，以確保網路防火牆設定只允許授權的連線。 Microsoft 365 系統、相依性及外部連線都會記錄在 Microsoft 365 的資訊安全性架構中。 資訊安全架構和對應的資料流程圖都會至少每年進行檢查及更新，而且每當對系統進行重大變更時，也會進行更新。

Microsoft 365 架構會定期進行驗證，並自動使用雲端架構工具來驗證與我們的安全性原則對齊，並持續測試隔離和恢復功能。 架構驗證可讓您自動識別目前服務的目前狀態已正軌至所需狀態的實例，並會標記出任何偏差以進行審閱與緩解。 架構驗證的目標是確保服務基礎結構的安全性功能仍可如預期的方式運作。

## <a name="related-external-regulations--certifications"></a>相關的外部法規 & 認證

Microsoft 的線上服務會定期進行審核，以符合外部法規和認證。 請參閱下表，以驗證與 Microsoft 365 架構相關的控制項。

| **外部審計** | **Section** | **最新報告日期** |
|:--------------------|:------------|:-----------------------|
| [FedRAMP (Office 365) ](https://compliance.microsoft.com/compliancemanager) | AC-4：資訊流執行 <br> CP-9：資訊系統備份 <br> PL-8：資訊安全架構 <br> SC-7：界限保護 <br> SC-22：架構與布建 | 2020年9月24日 |
| [ISO 27001/27002 (Office 365) ](https://servicetrust.microsoft.com/ViewPage/MSComplianceGuideV3?command=Download&downloadType=Document&downloadId=8d625374-4f2d-49f8-9d37-a4281ba98222&tab=7027ead0-3d6b-11e9-b9e1-290b1eb4cdeb&docTab=7027ead0-3d6b-11e9-b9e1-290b1eb4cdeb_ISO_Reports) <br><br> [適用性聲明](https://servicetrust.microsoft.com/ViewPage/MSComplianceGuideV3?command=Download&downloadType=Document&downloadId=c0df4ce8-c77e-4183-84eb-c8688470d8b1&tab=7027ead0-3d6b-11e9-b9e1-290b1eb4cdeb&docTab=7027ead0-3d6b-11e9-b9e1-290b1eb4cdeb_ISO_Reports) <br> [認證](https://servicetrust.microsoft.com/ViewPage/MSComplianceGuideV3?command=Download&downloadType=Document&downloadId=1e84a14a-2468-45ac-9412-5e53250d57ec&tab=7027ead0-3d6b-11e9-b9e1-290b1eb4cdeb&docTab=7027ead0-3d6b-11e9-b9e1-290b1eb4cdeb_ISO_Reports) | 6：資訊安全性的組織 <br> 13.1：網路安全性管理 <br> 17.2：冗余 | 2021 年 4 月 20 日 |
| [ISO 27017 (Office 365) ](https://servicetrust.microsoft.com/ViewPage/MSComplianceGuideV3?command=Download&downloadType=Document&downloadId=8d625374-4f2d-49f8-9d37-a4281ba98222&tab=7027ead0-3d6b-11e9-b9e1-290b1eb4cdeb&docTab=7027ead0-3d6b-11e9-b9e1-290b1eb4cdeb_ISO_Reports) <br><br> [適用性聲明](https://servicetrust.microsoft.com/ViewPage/MSComplianceGuideV3?command=Download&downloadType=Document&downloadId=c0df4ce8-c77e-4183-84eb-c8688470d8b1&tab=7027ead0-3d6b-11e9-b9e1-290b1eb4cdeb&docTab=7027ead0-3d6b-11e9-b9e1-290b1eb4cdeb_ISO_Reports) <br> [認證](https://servicetrust.microsoft.com/ViewPage/MSComplianceGuideV3?command=Download&downloadType=Document&downloadId=70de0999-5451-43a3-9ef4-761e8fbfb1a3&tab=7027ead0-3d6b-11e9-b9e1-290b1eb4cdeb&docTab=7027ead0-3d6b-11e9-b9e1-290b1eb4cdeb_ISO_Reports) | 6：資訊安全性的組織 <br> 13.1：網路安全性管理 | 2021 年 4 月 20 日 |
| [SOC 1 (Office 365) ](https://servicetrust.microsoft.com/ViewPage/MSComplianceGuideV3?command=Download&downloadType=Document&downloadId=90df3f9c-3aaf-4dbf-99d0-ca9f2991721b&tab=7027ead0-3d6b-11e9-b9e1-290b1eb4cdeb&docTab=7027ead0-3d6b-11e9-b9e1-290b1eb4cdeb_SOC_%2F_SSAE_16_Reports) | CA-37：租使用者隔離 <br> CA-49：備份原則 <br> CA-51：資料複寫 | 2020月24日 |
| [SOC 2 (Office 365) ](https://servicetrust.microsoft.com/ViewPage/MSComplianceGuideV3?command=Download&downloadType=Document&downloadId=a73c1738-7892-42b7-acd3-87b6371c53f6&tab=7027ead0-3d6b-11e9-b9e1-290b1eb4cdeb&docTab=7027ead0-3d6b-11e9-b9e1-290b1eb4cdeb_SOC_%2F_SSAE_16_Reports) | CA-05：資料流程圖 <br> CA-37：租使用者隔離 <br> CA-49：備份原則 <br> CA-51：資料複寫 | 2020月24日 |