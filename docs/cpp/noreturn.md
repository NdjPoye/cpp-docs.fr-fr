---
title: noreturn | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- noreturn_cpp
dev_langs:
- C++
helpviewer_keywords:
- __declspec keyword [C++], noreturn
- noreturn __declspec keyword
ms.assetid: 9c6517e5-22d7-4051-9974-3d2200ae4d1d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 90fab865a02b7ad00bd25b6d74f2d19b2678875c
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
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