---
title: Erreur du compilateur C2157 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C2157
dev_langs: C++
helpviewer_keywords: C2157
ms.assetid: babbca24-16dc-4b69-be14-a675029249c1
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 365218bccff744be577e5abf2a1472e40edccf7d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2157"></a>Erreur du compilateur C2157
'function' : doit être déclaré(e) avant d’être utilisé(e) dans une liste pragma  
  
 Le nom de la fonction n’est pas déclaré avant d’être référencé dans la liste des fonctions pour un pragma [alloc_text](../../preprocessor/alloc-text.md) .  
  
 L’exemple suivant génère l’erreur C2157 :  
  
```  
// C2157.cpp  
// compile with: /c  
#pragma alloc_text( "func", func)   // C2157  
  
// OK  
extern "C" void func();  
#pragma alloc_text( "func", func)  
```