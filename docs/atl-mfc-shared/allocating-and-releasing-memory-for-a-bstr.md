---
title: "Allocation et libération de mémoire pour un BSTR | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: bstr
dev_langs: C++
helpviewer_keywords:
- BSTRs, memory allocation
- memory deallocation, string memory
- memory [C++], releasing
- memory allocation, BSTRs
- memory deallocation, BSTR memory
- strings [C++], releasing
ms.assetid: 98041e29-3442-4a02-b425-7a4a13e9cc84
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 9b202d9e1d93cb170325ede736eb1ab33fc69b02
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="allocating-and-releasing-memory-for-a-bstr"></a>Allocation et libération de mémoire pour un BSTR
Lorsque vous créez `BSTR`s et les passer entre les objets COM, vous devez être attentif dans le traitement de la mémoire qu’ils utilisent afin d’éviter les fuites de mémoire. Lorsqu’un `BSTR` reste dans une interface, vous devez libérer sa mémoire lorsque vous avez terminé avec lui. Toutefois, lorsqu’un `BSTR` passe en dehors d’une interface, l’objet récepteur assume la responsabilité de la gestion de la mémoire.  
  
 En général, les règles pour l’allocation et libération de la mémoire allouée pour `BSTR`s sont les suivantes :  
  
-   Lorsque vous appelez une fonction qui attend un `BSTR` argument, vous devez allouer la mémoire pour le `BSTR` avant l’appel et libérer ensuite. Exemple :  
  
     [!code-cpp[NVC_ATLMFC_Utilities#192](../atl-mfc-shared/codesnippet/cpp/allocating-and-releasing-memory-for-a-bstr_1.cpp)]  
  
     [!code-cpp[NVC_ATLMFC_Utilities#193](../atl-mfc-shared/codesnippet/cpp/allocating-and-releasing-memory-for-a-bstr_2.cpp)]  
  
-   Lorsque vous appelez une fonction qui retourne un `BSTR`, vous devez libérer la chaîne vous-même. Exemple :  
  
     [!code-cpp[NVC_ATLMFC_Utilities#194](../atl-mfc-shared/codesnippet/cpp/allocating-and-releasing-memory-for-a-bstr_3.cpp)]  
  
     [!code-cpp[NVC_ATLMFC_Utilities#195](../atl-mfc-shared/codesnippet/cpp/allocating-and-releasing-memory-for-a-bstr_4.cpp)]  
  
-   Lorsque vous implémentez une fonction qui retourne un `BSTR`, allouez la chaîne mais ne le libérez pas. La réception de la fonction libère la mémoire. Exemple :  
  
     [!code-cpp[NVC_ATLMFC_Utilities#196](../atl-mfc-shared/codesnippet/cpp/allocating-and-releasing-memory-for-a-bstr_5.cpp)]  
  
## <a name="see-also"></a>Voir aussi  
 [Chaînes (ATL/MFC)](../atl-mfc-shared/strings-atl-mfc.md)   
 [CStringT::AllocSysString](../atl-mfc-shared/reference/cstringt-class.md#allocsysstring)   
 [SysAllocString](https://msdn.microsoft.com/library/windows/desktop/ms221458.aspx)   
 [SysFreeString](https://msdn.microsoft.com/library/windows/desktop/ms221481.aspx)

