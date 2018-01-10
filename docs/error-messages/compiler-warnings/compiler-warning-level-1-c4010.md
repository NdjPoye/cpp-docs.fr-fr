---
title: Compilateur avertissement (niveau 1) C4010 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4010
dev_langs: C++
helpviewer_keywords: C4010
ms.assetid: d607a9ff-8f8f-45c0-b07b-3b2f439e5485
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 1a56adb54c4a4b7123bde706a2b6b8bdcb184775
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4010"></a>Compilateur avertissement (niveau 1) C4010
commentaire sur une ligne contient le caractère de continuation de ligne  
  
 Un commentaire sur une ligne, commençant par / /, contient une barre oblique inverse (\\) qui sert d’un caractère de continuation de ligne. Le compilateur considère que la ligne suivante est une suite et le traite comme un commentaire.  
  
 Certains syntaxiques éditeurs n’indiquent pas la ligne qui suit le caractère de continuation en tant que commentaire. Ignorer les couleurs de syntaxe sur les lignes qui entraînent cet avertissement.  
  
 L’exemple suivant génère l’erreur C4010 :  
  
```  
// C4010.cpp  
// compile with: /WX  
int main() {  
   // the next line is also a comment because of the backslash \  
   int a = 3; // C4010  
   a++;  
}  
```