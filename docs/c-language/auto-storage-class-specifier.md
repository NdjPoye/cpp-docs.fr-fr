---
title: "Spécificateur de classe de stockage auto │ Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 8e73f57e-aa92-4e41-91ea-5c8ad2a2b332
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ce3ac6467ea566ebdd9d21e24843efe72457ba9e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="auto-storage-class-specifier"></a>Spécificateur de classe de stockage auto
Le spécificateur de classe de stockage **auto** déclare une variable automatique, une variable avec une durée de vie locale. Une variable **auto** est visible uniquement dans le bloc dans lequel elle est déclarée. Les déclarations de variables **auto** peuvent inclure des initialiseurs, comme indiqué dans [Initialisation](../c-language/initialization.md). Les variables avec la classe de stockage **auto** ne sont pas initialisées automatiquement, vous devez soit explicitement les initialiser lorsque vous les déclarez, ou leur assigner des valeurs initiales des instructions dans le bloc. Les valeurs des variables **auto** non initialisées sont éliminées. (Une variable locale **auto** ou une classe de stockage **register** est initialisée chaque fois qu'elle est dans la portée si un initialiseur est donné.)  
  
 Une variable interne **statique** (une variable statique avec une portée de bloc ou locale) peut être initialisée avec l’adresse de tout élément externe ou **statique**, mais pas avec l’adresse d’un autre élément **auto**, car l’adresse d’un élément **auto** n’est pas une constante.  
  
## <a name="see-also"></a>Voir aussi  
 [auto, mot clé](../cpp/auto-keyword.md)