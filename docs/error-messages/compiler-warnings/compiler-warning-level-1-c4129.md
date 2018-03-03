---
title: Compilateur avertissement (niveau 1) C4129 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4129
dev_langs:
- C++
helpviewer_keywords:
- C4129
ms.assetid: a4190c64-4bfb-48fd-8e98-52720bc0d878
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 6405c7c156f34b49ab892304ee51a6b996ac2595
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4129"></a>Compilateur avertissement (niveau 1) C4129
'caractère' : caractère de séquence d’échappement non reconnu  
  
 Le `character` après une barre oblique inverse (\\) dans un caractère ou une chaîne constante n’est pas reconnu comme une séquence d’échappement valide. La barre oblique inverse est ignorée et pas imprimée. Le caractère suivant la barre oblique inverse est imprimé.  
  
 Pour imprimer une barre oblique inverse unique, spécifier une double barre oblique inverse (\\\\).  
  
 La norme C++, section 2.13.2 traite des séquences d’échappement.  
  
 L’exemple suivant génère l’erreur C4129 :  
  
```  
// C4129.cpp  
// compile with: /W1  
int main() {  
   char array1[] = "\/709";   // C4129  
   char array2[] = "\n709";   // OK  
}  
```