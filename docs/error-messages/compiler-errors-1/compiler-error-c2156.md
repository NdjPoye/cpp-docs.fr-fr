---
title: Erreur du compilateur C2156 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C2156
dev_langs: C++
helpviewer_keywords: C2156
ms.assetid: 136f9c67-2c27-4f61-b7e6-ccd202eca697
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 1be9525cea208347e16a0b6a41a7c696ff340083
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2156"></a>Erreur du compilateur C2156
pragma doit être à l'extérieur de la fonction  
  
 Un pragma qui doit être spécifié à un niveau global (en dehors d’un corps de fonction) se trouve dans une fonction.  
  
 L’exemple suivant génère l’erreur C2156 :  
  
```  
// C2156.cpp  
#pragma optimize( "l", on )   // OK  
int main() {  
   #pragma optimize( "l", on )   // C2156  
}  
```