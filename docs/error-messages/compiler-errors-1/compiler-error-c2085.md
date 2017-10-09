---
title: Erreur du compilateur C2085 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2085
dev_langs:
- C++
helpviewer_keywords:
- C2085
ms.assetid: 0a86785c-8e6f-481b-8c7b-412220c1950d
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 45805bbea2eca77ae81922088471e99de26be1e4
ms.contentlocale: fr-fr
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2085"></a>Erreur du compilateur C2085
'identificateur' : pas dans la liste de paramètres formels  
  
 L’identificateur a été déclaré dans une définition de fonction, mais pas dans la liste de paramètres formels. (C ANSI seulement)  
  
 L’exemple suivant génère l’erreur C2085 :  
  
```  
// C2085.c  
void func1( void )  
int main( void ) {}   // C2085  
```  
  
 Résolution possible :  
  
```  
// C2085b.c  
void func1( void );  
int main( void ) {}  
```  
  
 Sans le point-virgule, `func1()` ressemble à une définition de fonction, et non pas comme un prototype, donc `main` est défini dans `func1()`, erreur C2085 pour l’identificateur `main`.
