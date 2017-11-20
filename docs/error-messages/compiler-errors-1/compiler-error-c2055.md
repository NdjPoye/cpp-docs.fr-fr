---
title: Erreur du compilateur C2055 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2055
dev_langs: C++
helpviewer_keywords: C2055
ms.assetid: 6cec79cc-6bec-443f-9897-fbf5452718c7
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: c447d79179f3575230353b3db70717702b542b68
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2055"></a>Erreur du compilateur C2055
liste de paramètres formels attendue, non une liste de type  
  
 Une définition de fonction contient une liste de type de paramètre au lieu d’une liste de paramètres formels. C ANSI requiert des paramètres formels à être appelé à moins d’être void ou des points de suspension (`...`).  
  
 L’exemple suivant génère l’erreur C2055 :  
  
```  
// C2055.c  
// compile with: /c  
void func(int, char) {}  // C2055  
void func (int i, char c) {}   // OK  
```