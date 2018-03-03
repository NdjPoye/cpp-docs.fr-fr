---
title: Erreur du compilateur C2448 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2448
dev_langs:
- C++
helpviewer_keywords:
- C2448
ms.assetid: e255df3c-f861-4b4d-a193-8768cef061a5
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: cf628cb40be9c6f5dadf978983f86122a72f847f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2448"></a>Erreur du compilateur C2448
'identificateur' : initialiseur de style fonction semble être une définition de fonction  
  
 La définition de fonction est incorrecte.  
  
 Cette erreur peut résulter d’une liste formelle en langage C de style ancien.  
  
 L’exemple suivant génère l’erreur C2448 :  
  
```  
// C2448.cpp  
void func(c)  
   int c;  
{}   // C2448  
```