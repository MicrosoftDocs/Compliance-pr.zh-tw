---
title: 加密和金鑰管理概觀
description: 深入瞭解 Microsoft 365 中的加密和金鑰管理
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
ms.openlocfilehash: 5e46fdb5ddc3b1b80df0bcadf9054b9353a0dc8e
ms.sourcegitcommit: fb379d1110a9a86c7f9bab8c484dc3f4b3dfd6f0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/23/2021
ms.locfileid: "53088642"
---
# <a name="encryption-and-key-management-overview"></a>加密和金鑰管理概觀

## <a name="what-role-does-encryption-play-in-protecting-customer-content"></a>加密在保護客戶內容時會扮演什麼角色？

大部分的 Microsoft business 雲端服務都是多租戶服務，也就是說，客戶內容可能會與其他客戶儲存在相同的實體硬體上。 為了保護客戶內容的機密性，Microsoft 365 會使用一些最強和最安全的加密通訊協定，加密靜態和傳輸中的所有資料。

加密不是強存取控制的替代。 Microsoft 365 的存取控制原則為零，其上的存取權 (ZSA) 可保護客戶內容，避免 Microsoft 員工未經授權的存取。 加密是指在任何位置儲存客戶內容的機密性，以及防止內容在 Microsoft 365 系統之間或 Microsoft 365 與客戶之間傳輸時進行讀取的情況下，對存取控制進行補充。

## <a name="how-does-microsoft-365-encrypt-data-at-rest"></a>Microsoft 365 如何加密靜態資料？

Microsoft 365 中的所有客戶內容都受到一或多個加密形式的保護。 Microsoft 伺服器使用 BitLocker 來加密包含磁片磁碟機的磁片磁碟機，該磁片磁片磁碟機包含的容量層級的客戶內容。 BitLocker 所提供的加密，可在其他進程或控制項中的失誤時保護客戶內容 (例如，對包含客戶內容) 之磁片的存取控制或回收可能會造成未授權實體存取的情形。

Exchange Online、Microsoft Teams、SharePoint 線上及商務用 OneDrive 也會在應用層使用服務加密，以加密客戶內容。 服務加密在增強式加密保護之上提供版權保護和管理功能。 它也可讓 Windows 的作業系統和這些作業系統儲存或處理的客戶資料之間分開。

## <a name="how-does-microsoft-365-encrypt-data-in-transit"></a>Microsoft 365 如何加密資料傳輸？

Microsoft 365 產品和服務使用強大的傳輸通訊協定（例如 TLS），以防止未授權的協力廠商在客戶資料移動到網路時遭到竊聽。 中轉中的資料範例包括正在傳遞的郵件訊息、線上會議中進行的交談，或是資料中心之間複寫的檔案。

在 Microsoft 365 中，每當使用者的裝置與 microsoft 伺服器進行通訊，或 microsoft 伺服器與另一部伺服器通訊時，就會將資料視為「傳輸」。 Exchange Online、SharePoint 線上、Microsoft Teams 和 Office 線上都使用 TLS，以確保資料在傳輸期間保持機密。

## <a name="how-does-microsoft-365-manage-the-keys-used-for-encryption"></a>Microsoft 365 如何管理加密所使用的金鑰？

增強式加密的安全性，只是用來加密資料的金鑰。 Microsoft 會使用自己的安全性憑證來加密資料內傳輸的 TLS 連線。 針對靜態資料，使用完整大量加密金鑰加密 BitLocker 受保護的磁片區，該金鑰是使用大量的主金鑰進行加密，而該金鑰又會系結至伺服器中的受信任平臺模組 (TPM) 。 BitLocker 會使用 FIPS 相容的演算法，以確保加密金鑰永遠不會以明文儲存或傳送。

服務加密為客戶資料在 Exchange Online、Microsoft Teams、SharePoint 線上及商務用 OneDrive 中提供額外的加密層級。 服務加密為客戶提供兩個加密金鑰管理選項： Microsoft 管理金鑰或客戶金鑰。 使用 Microsoft 管理金鑰時，Microsoft 365 服務會自動產生並安全地儲存用於服務加密的根機碼。

若客戶需要控制其自己的根加密金鑰，即可利用服務加密與客戶金鑰。 使用客戶金鑰，客戶可以使用內部部署硬體服務模組 (HSM) 或 Azure Key Vault (AKV) 來產生自己的加密金鑰。 客戶根機碼儲存在 AKV 中，而這些機碼是用來加密客戶信箱資料或檔案的其中一個 keychains 的根。 客戶根機碼只能透過 Microsoft 365 的服務代碼進行資料加密，以間接方式存取，而且無法由 Microsoft 員工直接存取。

## <a name="related-external-regulations--certifications"></a>相關的外部法規 & 認證

Microsoft 的線上服務會定期進行審核，以符合外部法規和認證。 請參閱下表，以驗證與加密和金鑰管理相關的控制項。

| **外部審計** | **Section** | **最新報告日期** |
|:--------------------|:------------|:-----------------------|
| [FedRAMP (Office 365) ](https://compliance.microsoft.com/compliancemanager) | SC-8：傳輸機密性和完整性 <br> SC-13：使用密碼編譯 <br> SC-28：靜止資訊保護 <br>  | 2020年9月24日 |
| [ISO 27001/27002 (Office 365) ](https://servicetrust.microsoft.com/ViewPage/MSComplianceGuideV3?command=Download&downloadType=Document&downloadId=8d625374-4f2d-49f8-9d37-a4281ba98222&tab=7027ead0-3d6b-11e9-b9e1-290b1eb4cdeb&docTab=7027ead0-3d6b-11e9-b9e1-290b1eb4cdeb_ISO_Reports) <br><br> [適用性聲明](https://servicetrust.microsoft.com/ViewPage/MSComplianceGuideV3?command=Download&downloadType=Document&downloadId=c0df4ce8-c77e-4183-84eb-c8688470d8b1&tab=7027ead0-3d6b-11e9-b9e1-290b1eb4cdeb&docTab=7027ead0-3d6b-11e9-b9e1-290b1eb4cdeb_ISO_Reports) <br> [認證](https://servicetrust.microsoft.com/ViewPage/MSComplianceGuideV3?command=Download&downloadType=Document&downloadId=1e84a14a-2468-45ac-9412-5e53250d57ec&tab=7027ead0-3d6b-11e9-b9e1-290b1eb4cdeb&docTab=7027ead0-3d6b-11e9-b9e1-290b1eb4cdeb_ISO_Reports) | 10.1：加密控制項 <br> 18.1.5：加密控制項 | 2021 年 4 月 20 日 |
| [ISO 27017 (Office 365) ](https://servicetrust.microsoft.com/ViewPage/MSComplianceGuideV3?command=Download&downloadType=Document&downloadId=8d625374-4f2d-49f8-9d37-a4281ba98222&tab=7027ead0-3d6b-11e9-b9e1-290b1eb4cdeb&docTab=7027ead0-3d6b-11e9-b9e1-290b1eb4cdeb_ISO_Reports) <br><br> [適用性聲明](https://servicetrust.microsoft.com/ViewPage/MSComplianceGuideV3?command=Download&downloadType=Document&downloadId=c0df4ce8-c77e-4183-84eb-c8688470d8b1&tab=7027ead0-3d6b-11e9-b9e1-290b1eb4cdeb&docTab=7027ead0-3d6b-11e9-b9e1-290b1eb4cdeb_ISO_Reports) <br> [認證](https://servicetrust.microsoft.com/ViewPage/MSComplianceGuideV3?command=Download&downloadType=Document&downloadId=70de0999-5451-43a3-9ef4-761e8fbfb1a3&tab=7027ead0-3d6b-11e9-b9e1-290b1eb4cdeb&docTab=7027ead0-3d6b-11e9-b9e1-290b1eb4cdeb_ISO_Reports) | 10.1：加密控制項 <br> 18.1.5：加密控制項 | 2021 年 4 月 20 日 |
| [ISO 27018 (Office 365) ](https://servicetrust.microsoft.com/ViewPage/MSComplianceGuideV3?command=Download&downloadType=Document&downloadId=8d625374-4f2d-49f8-9d37-a4281ba98222&tab=7027ead0-3d6b-11e9-b9e1-290b1eb4cdeb&docTab=7027ead0-3d6b-11e9-b9e1-290b1eb4cdeb_ISO_Reports) <br><br> [適用性聲明](https://servicetrust.microsoft.com/ViewPage/MSComplianceGuideV3?command=Download&downloadType=Document&downloadId=c0df4ce8-c77e-4183-84eb-c8688470d8b1&tab=7027ead0-3d6b-11e9-b9e1-290b1eb4cdeb&docTab=7027ead0-3d6b-11e9-b9e1-290b1eb4cdeb_ISO_Reports) <br> [認證](https://servicetrust.microsoft.com/ViewPage/MSComplianceGuideV3?command=Download&downloadType=Document&downloadId=43e89534-f48d-42ea-a7a7-3523ff516036&tab=7027ead0-3d6b-11e9-b9e1-290b1eb4cdeb&docTab=7027ead0-3d6b-11e9-b9e1-290b1eb4cdeb_ISO_Reports) | 11.6：以公用資料傳輸網路傳輸之 PII 的加密 | 2021 年 4 月 20 日 |
| [SOC 2 (Office 365) ](https://servicetrust.microsoft.com/ViewPage/MSComplianceGuideV3?command=Download&downloadType=Document&downloadId=a73c1738-7892-42b7-acd3-87b6371c53f6&tab=7027ead0-3d6b-11e9-b9e1-290b1eb4cdeb&docTab=7027ead0-3d6b-11e9-b9e1-290b1eb4cdeb_SOC_%2F_SSAE_16_Reports) | CA-44：資料中轉加密 <br> CA-54：靜止資料加密 <br> CA-62：客戶金鑰信箱加密 <br> CA-63：刪除客戶金鑰資料 <br> CA-64：客戶金鑰 | 2020月24日 |
| [SOC 3 (Office 365) ](https://servicetrust.microsoft.com/ViewPage/MSComplianceGuideV3?command=Download&downloadType=Document&downloadId=274054e5-4968-48d2-bf94-9a8eda5d7a93&tab=7027ead0-3d6b-11e9-b9e1-290b1eb4cdeb&docTab=7027ead0-3d6b-11e9-b9e1-290b1eb4cdeb_SOC_%2F_SSAE_16_Reports) | CUEC-16：客戶加密金鑰 <br> CUEC-17：客戶金鑰保存庫 <br>  CUEC-18：客戶金鑰輪替| 2020月24日 |
