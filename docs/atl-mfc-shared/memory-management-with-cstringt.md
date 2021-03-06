---
title: Gestion de la mémoire avec CStringT | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CStringT
- ATL::CStringT
- ATL.CStringT
dev_langs:
- C++
helpviewer_keywords:
- CString objects, memory management
- memory [C++], usage
- IAtlStringMgr class, using
- strings [C++], custom memory management
- CFixedStringT class, description of
- strings [C++], memory management
- CStringT class, memory management
ms.assetid: 88b8342d-19b5-48c4-9cf6-e4c44cece21e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b65efd934fecdab36bfa1c0c882de1dd8862c81f
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="memory-management-with-cstringt"></a>Gestion de la mémoire avec CStringT
Classe [CStringT](../atl-mfc-shared/reference/cstringt-class.md) est une classe de modèle utilisée pour manipuler des chaînes de caractères de longueur variable. La mémoire pour stocker ces chaînes est allouée et publiée via un objet de gestionnaire de chaîne, associé à chaque instance de `CStringT`. MFC et ATL fournissent des instanciations par défaut de `CStringT`, appelé `CString`, `CStringA`, et `CStringW`, qui manipulent des chaînes de différents types de caractères. Ces types de caractères sont de type **TCHAR**, `char`, et `wchar_t`, respectivement. Ces types de chaîne par défaut utilisent un gestionnaire de chaînes qui alloue la mémoire à partir du tas de processus (dans ATL) ou du tas CRT (dans MFC). Pour les applications conventionnelles, cette méthode d’allocation de mémoire est suffisante. Toutefois, pour le code qui effectue beaucoup utiliser des chaînes (ou code multithread) les gestionnaires de mémoire par défaut ne soient pas optimales. Cette rubrique décrit comment substituer le comportement de gestion de mémoire par défaut de `CStringT`, création d’allocateurs spécifiquement optimisée pour la tâche en cours.  
  
-   [Implémentation d’un gestionnaire de chaînes personnalisé (méthode élémentaire)](../atl-mfc-shared/implementation-of-a-custom-string-manager-basic-method.md)  
  
-   [Éviter les conflits de tas](../atl-mfc-shared/avoidance-of-heap-contention.md)  
  
-   [Implémentation d’un gestionnaire de chaînes personnalisé (méthode avancée)](../atl-mfc-shared/implementation-of-a-custom-string-manager-advanced-method.md)  
  
-   [CFixedStringT : Un exemple d’un gestionnaire de chaîne personnalisé.](../atl-mfc-shared/cfixedstringt-example-of-a-custom-string-manager.md)  
  
## <a name="see-also"></a>Voir aussi  
 [Exemple CustomString](../visual-cpp-samples.md)

