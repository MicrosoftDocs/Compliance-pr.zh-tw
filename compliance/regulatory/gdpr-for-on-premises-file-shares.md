---
title: 適用於內部部署檔案共用的 GDPR
description: 瞭解如何解決內部部署 Windows Server 檔案共用中的一般資料保護規定 (GDPR) 需求。
f1.keywords:
- NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
titleSuffix: Microsoft GDPR
ms.custom: seo-marvel-apr2020
ms.collection: MS-Compliance
ms.openlocfilehash: 5a3b192e4c374dac4248300627e5659a1b5f66fd
ms.sourcegitcommit: 18c7e403d6ffbc9afa323fadc04c673dbb7bd391
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/10/2020
ms.locfileid: "49620758"
---
# <a name="gdpr-for-on-premises-windows-server-file-shares"></a><span data-ttu-id="ef4ba-103">適用於內部部署 Windows Server 檔案共用的 GDPR</span><span class="sxs-lookup"><span data-stu-id="ef4ba-103">GDPR for on-premises Windows Server file shares</span></span>

<span data-ttu-id="ef4ba-104">對於檔案共用的基本建議方法是：</span><span class="sxs-lookup"><span data-stu-id="ef4ba-104">The basic recommended approach for file shares is:</span></span>

-   <span data-ttu-id="ef4ba-105">使用 Azure 資訊保護來標記機密資料。</span><span class="sxs-lookup"><span data-stu-id="ef4ba-105">Use Azure Information Protection to label sensitive data.</span></span>

-   <span data-ttu-id="ef4ba-106">使用 Azure 資訊保護掃描器來尋找資料。</span><span class="sxs-lookup"><span data-stu-id="ef4ba-106">Use Azure Information Protection scanner to find data.</span></span>

<span data-ttu-id="ef4ba-107">檔案共用的建議方法包括下列步驟：</span><span class="sxs-lookup"><span data-stu-id="ef4ba-107">The recommended approach for files shares includes these steps:</span></span>

1.  <span data-ttu-id="ef4ba-108">**安裝及設定 Azure 資訊保護掃描器。**</span><span class="sxs-lookup"><span data-stu-id="ef4ba-108">**Install and configure Azure Information Protection scanner.**</span></span>

    -   <span data-ttu-id="ef4ba-109">決定要使用哪個機密資料類型。</span><span class="sxs-lookup"><span data-stu-id="ef4ba-109">Decide which sensitive data types to use.</span></span>

    -   <span data-ttu-id="ef4ba-110">指定要使用的本機資料夾和網路共用。</span><span class="sxs-lookup"><span data-stu-id="ef4ba-110">Specify local folders and network shares to use.</span></span>

2.  <span data-ttu-id="ef4ba-111">**完成探索循環。**</span><span class="sxs-lookup"><span data-stu-id="ef4ba-111">**Complete a discovery cycle.**</span></span>

    -   <span data-ttu-id="ef4ba-112">在探索模式中執行掃描器，並且驗證結果。</span><span class="sxs-lookup"><span data-stu-id="ef4ba-112">Run the scanner in discovery mode and validate the findings.</span></span>

    -   <span data-ttu-id="ef4ba-113">視需要最佳化條件和機密資訊類型。</span><span class="sxs-lookup"><span data-stu-id="ef4ba-113">If needed, optimize the conditions and sensitive information types.</span></span>

    -   <span data-ttu-id="ef4ba-114">評估自動套用標籤的預期影響。</span><span class="sxs-lookup"><span data-stu-id="ef4ba-114">Assess the expected impact of automatically applying labels.</span></span>

3.  <span data-ttu-id="ef4ba-115">**執行 Azure 資訊保護掃描器以將標籤套用至符合資格的文件**。</span><span class="sxs-lookup"><span data-stu-id="ef4ba-115">**Run the Azure Information Protection scanner to apply labels to qualifying documents**.</span></span>

4.  <span data-ttu-id="ef4ba-116">**針對保護：**</span><span class="sxs-lookup"><span data-stu-id="ef4ba-116">**For protection:**</span></span>

    -   <span data-ttu-id="ef4ba-117">設定 Exchange 資料外洩防護規則，保護具有所需標籤的文件。</span><span class="sxs-lookup"><span data-stu-id="ef4ba-117">Configure Exchange data loss prevention rules to protect documents with the desired label.</span></span>

    -   <span data-ttu-id="ef4ba-118">請務必使用權限來限制可以存取檔案的人員。</span><span class="sxs-lookup"><span data-stu-id="ef4ba-118">Be sure to use permissions to limit who can access files.</span></span>

5.  <span data-ttu-id="ef4ba-119">**針對監視，整合 Windows Server 記錄與 SIEM 工具。**</span><span class="sxs-lookup"><span data-stu-id="ef4ba-119">**For monitoring, integrate Windows Server logs with a SIEM tool.**</span></span>

    -   <span data-ttu-id="ef4ba-p101">若要針對資料主體要求尋找個人資料，請使用 Azure 資訊保護掃描器。您也可以設定 SharePoint Server 搜尋來對檔案共用進行編目。</span><span class="sxs-lookup"><span data-stu-id="ef4ba-p101">To find personal data for data subject requests, use Azure Information Protection scanner. You can also configure SharePoint Server search to crawl file shares.</span></span>

<span data-ttu-id="ef4ba-122">如需有關使用 Azure 資訊保護掃描器來找出個人資料並加上標籤的詳細資訊，請參閱 [部署 AIP 掃描程式](<https://docs.microsoft.com/azure/information-protection/deploy-aip-scanner)。</span><span class="sxs-lookup"><span data-stu-id="ef4ba-122">For more information on using Azure Information Protection scanner to find and label personal data, see [Deploy AIP Scanner](<https://docs.microsoft.com/azure/information-protection/deploy-aip-scanner).</span></span>

<span data-ttu-id="ef4ba-p102">如需有關針對條件設定掃描器，以及使用 Office 365 資料外洩防護 (DLP) 機密資訊類型的詳細資訊，請參閱＜[如何針對 Azure 資訊保護的自動和建議分類設定條件](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-classification)＞。請注意，新的 Office 365 機密資訊類型無法立即與掃描器搭配使用，且自訂機密資訊類型無法與掃描器搭配使用。</span><span class="sxs-lookup"><span data-stu-id="ef4ba-p102">For information on configuring the scanner for conditions and using the Office 365 data loss prevention (DLP) sensitive information types, see [How to configure conditions for automatic and recommended classification for Azure Information Protection](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-classification). Note that new Office 365 sensitive information types will not be immediately available to use with the scanner and custom sensitive information types cannot be used with the scanner.</span></span>
