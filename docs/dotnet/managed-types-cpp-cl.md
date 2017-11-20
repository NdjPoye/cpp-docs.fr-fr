---
title: "Types (C++-CL) managés | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- __gc types
- types [C++], CLR
ms.assetid: 1ddd114e-be02-4de7-a4dd-a2d72ad8ff81
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 058c2c2c2c8c54a0c4c7d290326c4af453c73d05
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="managed-types-ccl"></a>Types managés (C++/CL)
La syntaxe de la déclaration des types managés et à créer et utiliser des objets de ces types a été sensiblement modifiée entre les Extensions managées pour C++ vers Visual C++. Cela a été fait pour favoriser leur intégration dans le système de type ISO-C++. Ces modifications sont présentées en détail dans les sous-sections suivantes.  
  
## <a name="in-this-section"></a>Dans cette section  
 [Déclaration d’un type de classe managée](../dotnet/declaration-of-a-managed-class-type.md)  
 Explique comment déclarer `class`, `struct`, ou `interface`.  
  
 [Déclaration d’un objet de classe de référence du CLR](../dotnet/declaration-of-a-clr-reference-class-object.md)  
 Explique comment déclarer un objet de type de classe de référence à l’aide d’un handle de suivi.  
  
 [Déclaration d’un tableau CLR](../dotnet/declaration-of-a-clr-array.md)  
 Explique comment déclarer et initialiser un tableau.  
  
 [Modifications dans l’ordre d’initialisation des constructeurs](../dotnet/changes-in-constructor-initialization-order.md)  
 Traite des principales modifications dans l’ordre de l’initialisation de constructeur de classe.  
  
 [Modifications de la sémantique du destructeur](../dotnet/changes-in-destructor-semantics.md)  
 Traite de finalisation non déterministe, `Finalize` et `Dispose`, ramifications pour les objets de référence et l’utilisation d’explicite `Finalize`.  
  
 **Remarque :** la discussion des délégués est différée jusqu'à ce que [délégués et événements](../dotnet/delegates-and-events.md) afin de les présenter avec les membres d’événement dans une classe, le sujet général de [déclarations de membre dans une classe ou une Interface (C + C++ / CLI) ](../dotnet/member-declarations-within-a-class-or-interface-cpp-cli.md).  
  
## <a name="see-also"></a>Voir aussi  
 [C + c++ / CLI Initiation à la Migration](../dotnet/cpp-cli-migration-primer.md)   
 [Classes et structs](../windows/classes-and-structs-cpp-component-extensions.md)   
 [Tableaux](../windows/arrays-cpp-component-extensions.md)