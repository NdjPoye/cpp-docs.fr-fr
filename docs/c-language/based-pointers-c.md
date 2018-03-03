---
title: "Pointeurs basés sur (C) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- __based keyword [C]
- based pointers
- pointers, based
- based addressing
ms.assetid: b5446920-89e0-4e2f-91f3-1f2a769a08e8
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f90e21bc2a7557dee7044ffe106df51552dd5666
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="based-pointers-c"></a>Pointeurs basés sur (C)
**Section spécifique à Microsoft**  
  
 [__based (référence C++)](../cpp/based-pointers-cpp.md)  
  
 Pour les compilateurs C 32 bits et 64 bits de Microsoft, un pointeur based est un décalage 32 bits ou 64 bits par rapport à une base de pointeur 32 bits ou 64 bits. L'adressage est utile pour exercer un contrôle sur les sections dans lesquelles les objets sont alloués, ce qui permet de réduire la taille du fichier exécutable et d'augmenter la vitesse d'exécution. En général, la forme pour spécifier un pointeur based est la suivante :  
  
```  
  
type  
__based(  
base  
)  
declarator  
  
```  
  
 La variante « basé sur le pointeur » de l'adressage based permet de spécifier un pointeur comme base. Le pointeur based représente alors un décalage dans la section de mémoire qui démarre au début du pointeur sur lequel il est basé. Les pointeurs basés sur des adresses de pointeur sont la seule forme valide du mot clé `__based` dans les compilations 32 bits et 64 bits. Dans ces compilations, ils représentent des déplacements 32 bits ou 64 bits par rapport à une base 32 bits ou 64 bits.  
  
 Les pointeurs basés sur pointeurs peuvent par exemple être utilisés pour des identificateurs persistants qui contiennent des pointeurs. Une liste liée composée de pointeurs basés sur un pointeur peut être enregistrée sur le disque, puis rechargée dans un autre emplacement mémoire, et les pointeurs restent valides.  
  
 L'exemple suivant illustre un pointeur basé sur un autre pointeur.  
  
```  
void *vpBuffer;  
  
struct llist_t  
{  
    void __based( vpBuffer ) *vpData;  
    struct llist_t __based( vpBuffer ) *llNext;  
};  
```  
  
 Le pointeur `vpBuffer` reçoit l'adresse de la mémoire allouée à un point ultérieur dans le programme. La liste liée est déplacée par rapport à la valeur de `vpBuffer`.  
  
 **FIN de la section spécifique à Microsoft**  
  
## <a name="see-also"></a>Voir aussi  
 [Déclarateurs et déclarations de variable](../c-language/declarators-and-variable-declarations.md)