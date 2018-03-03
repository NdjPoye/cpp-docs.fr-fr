---
title: "Conception de Collection et les Interfaces d’énumérateur (ATL) | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- enumerator interfaces
- collection interfaces
ms.assetid: ea19a39e-6333-41a1-be62-5435c236640e
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8709274e1b95816dee01b4457993521dde5d5213
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="design-principles-for-collection-and-enumerator-interfaces"></a>Principes de conception pour la collecte et les Interfaces d’énumérateur
Il existe des principes de conception de chaque type d’interface :  
  
-   Une interface de collection fournit *aléatoires* l’accès à un *unique* élément dans la collection via la **élément** (méthode), il permet aux clients de découvrir le nombre d’éléments figurant dans la collection via le **nombre** propriété, et souvent permet aux clients d’ajouter et supprimer des éléments.  
  
-   Une interface d’énumérateur fournit *série* l’accès à *plusieurs* les éléments d’une collection, il n’autorise pas le client découvrir le nombre d’éléments figurant dans la collection (jusqu'à ce que l’énumérateur cesse de retour éléments), et il ne fournit aucun moyen d’Ajout ou suppression d’éléments.  
  
 Chaque type d’interface joue un rôle différent en fournissant l’accès aux éléments dans une collection.  
  
## <a name="see-also"></a>Voir aussi  
 [Collections et énumérateurs](../atl/atl-collections-and-enumerators.md)

