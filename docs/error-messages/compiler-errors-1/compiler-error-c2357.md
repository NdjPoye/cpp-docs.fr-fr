---
title: Erreur du compilateur C2357 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2357
dev_langs: C++
helpviewer_keywords: C2357
ms.assetid: d1083945-0ea2-4385-9e66-8c665978806c
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 46fe3b489f32b7eb0243b1b5cb03d04b69b38c95
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2357"></a>Erreur du compilateur C2357
'identificateur' : doit être une fonction de type 'type'  
  
 Votre code déclare une version de la `atexit` fonction qui ne correspond pas à la version déclarée en interne par le compilateur. Déclarer `atexit` comme suit :  
  
```  
int __cdecl atexit(void (__cdecl *)());  
```  
  
 Pour plus d’informations, consultez [init_seg](../../preprocessor/init-seg.md).  
  
 L’exemple suivant génère l’erreur C2357 :  
  
```  
// C2357.cpp  
// compile with: /c  
// C2357 expected  
#pragma warning(disable : 4075)  
// Uncomment the following line to resolve.  
// int __cdecl myexit(void (__cdecl *)());  
#pragma init_seg(".mine$m",myexit)  
```