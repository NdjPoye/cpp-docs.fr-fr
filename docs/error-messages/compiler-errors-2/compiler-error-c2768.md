---
title: Erreur du compilateur C2768 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2768
dev_langs: C++
helpviewer_keywords: C2768
ms.assetid: a7f6047a-6a80-4737-ad5c-c12868639fb5
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 42f4c23f36669ae2dd3284d8902f6ba017617201
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2768"></a>Erreur du compilateur C2768
'fonction' : utilisation non conforme d’arguments template explicites  
  
 Le compilateur n’a pas pu déterminer si une définition de fonction est censé pour être une spécialisation explicite d’un modèle de fonction ou si la définition de fonction est censé pour être d’une nouvelle fonction.  
  
 Cette erreur a été introduite dans Visual Studio .NET 2003, dans le cadre de ces améliorations de mise en conformité du compilateur.  
  
 L’exemple suivant génère l’erreur C2768 :  
  
```  
// C2768.cpp  
template<typename T>  
void f(T) {}  
  
void f<int>(int) {}   // C2768  
  
// an explicit specialization  
template<>  
void f<int>(int) {}   
  
// global nontemplate function overload  
void f(int) {}  
```