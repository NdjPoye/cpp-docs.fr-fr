---
title: Erreur du compilateur C2002 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2002
dev_langs:
- C++
helpviewer_keywords:
- C2002
ms.assetid: 91982314-203a-4de1-b884-94e39a623f61
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: d8f6fc5983a462850581f69ca32dd7c305f9e847
ms.contentlocale: fr-fr
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2002"></a>Erreur du compilateur C2002
constante à caractères larges non valide  
  
 La constante à caractères multioctets n’est pas valide.  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>Pour corriger en vérifiant les causes possibles suivantes  
  
1.  La constante à caractères larges contient plus d’octets que prévu.  
  
2.  L’en-tête standard STDDEF.h n’est pas inclus.  
  
3.  Caractères larges ne peut pas être concaténés avec des littéraux de chaîne ordinaires.  
  
4.  Une constante à caractères larges doit être précédée par le caractère « L » :  
  
    ```  
    L'mbconst'  
    ```  
  
5.  Pour Microsoft C++, les arguments de texte d’une directive de préprocesseur doivent être ASCII. Par exemple, la directive, `#pragma message(L"string")`, n’est pas valide.
