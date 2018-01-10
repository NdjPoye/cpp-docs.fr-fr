---
title: Erreur du compilateur C2356 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2356
dev_langs: C++
helpviewer_keywords: C2356
ms.assetid: 84d5a816-9a61-4d45-9978-38e485bbf767
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a09e44133b6bea0f79df020b359719cf1a1754c8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2356"></a>Erreur du compilateur C2356
un segment d’initialisation ne doit pas changer au cours de l’unité de traduction  
  
 Causes possibles :  
  
-   `#pragma init_seg`précédé par un code d’initialisation de segments  
  
-   `#pragma init_seg`précédé par un autre`#pragma init_seg`  
  
 Pour résoudre, déplacez le code d’initialisation de segments au début du module. Si plusieurs zones doivent être initialisées, déplacez-les dans des modules séparés.  
  
 L’exemple suivant génère l’erreur C2356 :  
  
```  
// C2356.cpp  
#pragma warning(disable : 4075)  
  
int __cdecl myexit(void (__cdecl *)());  
int __cdecl myexit2(void (__cdecl *)());  
  
#pragma init_seg(".mine$m",myexit)  
#pragma init_seg(".mine$m",myexit2)   // C2356  
```