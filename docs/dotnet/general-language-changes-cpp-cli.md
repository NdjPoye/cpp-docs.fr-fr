---
title: "Modifications du langage général (C + c++ / CLI) | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 79a70768-225c-4ae2-84d1-178b20a9b042
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 87ff7f55b67c4e8a84d15099432962ee0939d13a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="general-language-changes-ccli"></a>Modifications d'ordre général apportées au langage (C++/CLI)
Nombre de fonctionnalités du langage CLR changé entre les Extensions managées pour C++ vers Visual C++.  
  
 Les modifications décrites dans cette section sont une sorte de sorte de pot-pourri de langage. Il inclut une modification dans la gestion des littéraux de chaîne, une modification de la résolution de surcharge entre des points de suspension et la `Param` d’attribut, la modification de `typeof` à `typeid`, une modification de l’appel des listes d’initialiseurs de constructeur et le introduction d’une nouvelle notation de cast, celle de `safe_cast`.  
  
 [Littéral de chaîne](../dotnet/string-literal.md)  
 Explique comment la gestion des littéraux de chaîne a changé.  
  
 [Tableau Param et points de suspension](../dotnet/param-array-and-ellipsis.md)  
 Explique comment `ParamArray` est désormais priorité sur les points de suspension (`...`) pour résoudre des appels de fonction avec un nombre variable d’arguments.  
  
 [typeof va à T::typeid](../dotnet/typeof-goes-to-t-typeid.md)  
 Explique comment la `typeof` opérateur a été supplanté par `typeid`.  
  
 [Listes d’initialiseurs](../dotnet/initializer-lists.md)  
 Traite des modifications dans l’ordre d’appel des listes d’initialiseurs.  
  
 [Notation castée et introduction de safe_cast](../dotnet/cast-notation-and-introduction-of-safe-cast-angles.md)  
 Traite des modifications apportées à la notation de cast et en particulier l’introduction de `safe_cast`.  
  
## <a name="see-also"></a>Voir aussi  
 [Initiation à la migration de C++/CLI](../dotnet/cpp-cli-migration-primer.md)