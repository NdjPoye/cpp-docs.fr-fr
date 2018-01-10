---
title: "Règles prédéfinies | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- rules, predefined
- NMAKE program, predefined rules
- predefined rules in NMAKE
ms.assetid: 638cdc3f-4aba-4b4f-96e3-ad65b0364f12
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 3be1c8eea7b11f60e9ce9a7cbf5ebc0c2b99b698
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="predefined-rules"></a>Règles prédéfinies
Règles d’inférence prédéfinies utilisent les macros de commande et les options fournies par NMAKE.  
  
|Règle|Commande|Par défaut<br /><br /> action|Batch<br /><br /> Règle|La plateforme nmake s’exécute sur|  
|----------|-------------|------------------------|--------------------|----------------------------|  
|. asm.exe|$(AS) $(AFLAGS) $<|ml $<|Non|x86|  
|. asm.obj|$(AS) $(AFLAGS) /c $<|ml /c $<|oui|x86|  
|. asm.exe|$(AS) $(AFLAGS) $<|ml64 $<|Non|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
|. asm.obj|$(AS) $(AFLAGS) /c $<|ml64 /c $<|oui|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
|. c.exe|$(CC) $(CFLAGS) $<|CL $<|non|toutes les|  
|. c.obj|$(CC) $(CFLAGS) /c $<|cl /c $<|oui|toutes les|  
|. cc.exe|$(CC) $(CFLAGS) $<|CL $<|non|toutes les|  
|. cc.obj|$(CC) $(CFLAGS) /c $<|cl /c $<|oui|toutes les|  
|. cpp.exe|$(CPP) $(CPPFLAGS) $<|CL $<|non|toutes les|  
|. cpp.obj|$(CPP) $(CPPFLAGS) /c $<|cl /c $<|oui|toutes les|  
|. cxx.exe|$(CXX) $(CXXFLAGS) $<|CL $<|non|toutes les|  
|. cxx.obj|$(CXX) $(CXXFLAGS) /c $<|cl /c $<|oui|toutes les|  
|. rc.res|$(RC) $(RFLAGS) /r $<|/r rc $<|Non|toutes les|  
  
## <a name="see-also"></a>Voir aussi  
 [Règles d’inférence](../build/inference-rules.md)