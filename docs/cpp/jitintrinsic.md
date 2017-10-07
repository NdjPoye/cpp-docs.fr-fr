---
title: jitintrinsic | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- jitintrinsic
- jitintrinsic_cpp
dev_langs:
- C++
helpviewer_keywords:
- __declspec keyword [C++], jitintrinsic
- jitintrinsic __declspec modifier
ms.assetid: 23dbe416-7ef6-442b-b16d-9a81aab04fa6
caps.latest.revision: 8
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 6712a62aaff0ff903117da87364cae5bc88580fd
ms.contentlocale: fr-fr
ms.lasthandoff: 09/25/2017

---
# <a name="jitintrinsic"></a>jitintrinsic
Marque la fonction comme significative pour le CLR (Common Langage Runtime) 64 bits. Ceci est utilisé pour certaines fonctions dans les bibliothèques fournies par Microsoft.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
__declspec(jitintrinsic)  
```  
  
## <a name="remarks"></a>Remarques  
 `jitintrinsic` ajoute un MODOPT (<xref:System.Runtime.CompilerServices.IsJitIntrinsic>) à la signature de la fonction.  
  
 Il est déconseillé aux utilisateurs d'avoir recours à ce modificateur `__declspec`, car des résultats inattendus peuvent survenir.  
  
## <a name="see-also"></a>Voir aussi  
 [__declspec](../cpp/declspec.md)   
 [Mots clés](../cpp/keywords-cpp.md)
