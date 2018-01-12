---
title: Erreur du compilateur C2379 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2379
dev_langs: C++
helpviewer_keywords: C2379
ms.assetid: 37dc3015-a4af-4341-bbf3-da6150df7e51
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d39a94722563a9feef7914f092968f1754d0d429
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2379"></a>Erreur du compilateur C2379
nombre de paramètres formels a un type différent lors de sa promotion  
  
 Le type du paramètre spécifié n’est pas compatible, via les promotions par défaut, avec le type d’une déclaration précédente. Il s’agit d’une erreur en C ANSI ([/Za](../../build/reference/za-ze-disable-language-extensions.md)) et un avertissement avec les extensions Microsoft (**/Ze**).  
  
 L’exemple suivant génère C2379 :  
  
```  
// C2379.c  
// compile with: /Za  
void func();  
void func(char);   // C2379, char promotes to int  
```