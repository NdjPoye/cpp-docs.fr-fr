---
title: noreturn | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: noreturn_cpp
dev_langs: C++
helpviewer_keywords:
- __declspec keyword [C++], noreturn
- noreturn __declspec keyword
ms.assetid: 9c6517e5-22d7-4051-9974-3d2200ae4d1d
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 91c6a7b38653a3bb0a86927ced602fd85ff29277
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="noreturn"></a>noreturn
## <a name="microsoft-specific"></a>Section spécifique à Microsoft  
 Cet attribut `__declspec` indique au compilateur qu'une fonction ne retourne pas. Par conséquent, le compilateur sait que le code suivant d’un appel à une **__declspec (noreturn)** fonction n’est pas accessible.  
  
 Si le compilateur recherche une fonction avec un chemin d’accès au contrôle qui ne retourne pas de valeur, il génère un avertissement (C4715) ou le message d’erreur (C2202). Si le chemin d’accès de contrôle ne peut pas être atteint en raison d’une fonction qui ne retourne jamais, vous pouvez utiliser **__declspec (noreturn)** pour éviter cet avertissement ou une erreur.  
  
> [!NOTE]
>  Ajout de **__declspec (noreturn)** à une fonction censée retourner peut entraîner un comportement non défini.  
  
## <a name="example"></a>Exemple  
 Dans l’exemple suivant, la **else** clause ne contient pas une instruction return.  Déclaration `fatal` en tant que **__declspec (noreturn)** permet d’éviter une erreur ou un message d’avertissement.  
  
```  
// noreturn2.cpp  
__declspec(noreturn) extern void fatal () {}  
  
int main() {  
   if(1)  
     return 1;  
   else if(0)  
     return 0;  
   else  
     fatal();  
}  
```  
  
## <a name="see-also"></a>Voir aussi  
 [__declspec](../cpp/declspec.md)   
 [Mots clés](../cpp/keywords-cpp.md)