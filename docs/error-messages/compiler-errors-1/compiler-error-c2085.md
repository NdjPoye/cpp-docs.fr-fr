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
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 5834cbca32c2e3bb0c20ab39ee5d3b9d3e8e9c55
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
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
  
 Solution possible :  
  
```  
// C2085b.c  
void func1( void );  
int main( void ) {}  
```  
  
 Sans le point-virgule, `func1()` ressemble à une définition de fonction, et non pas comme un prototype, donc `main` est défini dans `func1()`, erreur C2085 pour l’identificateur `main`.