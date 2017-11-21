---
title: Compilateur avertissement (niveau 1) C4566 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4566
dev_langs: C++
helpviewer_keywords: C4566
ms.assetid: 65f40730-e86f-447c-b37b-16caadcfe311
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 7d2755a8e4220f45ef243153b0d0da7b95ec15b4
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-1-c4566"></a>Avertissement du compilateur (niveau 1) C4566
caractère représenté par le nom de caractère universel 'char' ne peut pas être représenté dans la page de codes actuelle (page)  
  
 Pas tous les caractères Unicode peuvent être représentés dans votre page de codes ANSI actuelle.  
  
 Les chaînes étroites (caractères à un octet) sont convertis en caractères multioctets alors que les chaînes étendues (caractères sur deux octets) ne sont pas.  
  
 L’exemple suivant génère l’erreur C4566 :  
  
```  
// C4566.cpp  
// compile with: /W1  
int main() {  
   char c1 = '\u03a0';   // C4566  
   char c2 = '\u0642';   // C4566  
  
   wchar_t c3 = L'\u03a0';   // OK  
   wchar_t c4 = L'\u0642';   // OK  
}  
```