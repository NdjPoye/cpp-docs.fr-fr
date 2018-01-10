---
title: "2.7.2.5 la valeur par défaut | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: c856df07-705c-4ad3-9105-a268dd33e939
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 1ee328be7f9f0c4876738f8179c26e700c57702c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="2725-default"></a>2.7.2.5 default
Le **par défaut** clause permet à l’utilisateur affecter les attributs de partage de données de variables. La syntaxe de la **par défaut** clause est comme suit :  
  
```  
default(shared | none)  
```  
  
 Spécification de **default(shared)** équivaut à répertoriant explicitement chaque variable actuellement visible dans un **partagé** clause, sauf s’il est **threadprivate** ou **inconvénients**`t`-qualifié. En l’absence d’explicite **par défaut** clause, le comportement par défaut est le même qu’if **default(shared)** ont été spécifiés.  
  
 Spécification de **default (None)** requiert qu’au moins une des valeurs suivantes doit être remplie pour chaque référence à une variable dans l’étendue lexicale de la construction parallèle :  
  
-   La variable est explicitement répertoriée dans une clause partage des données d’attribut d’une construction qui contient la référence.  
  
-   La variable est déclarée au sein de la construction parallèle.  
  
-   La variable est **threadprivate**.  
  
-   La variable a une **const**-type qualifié.  
  
-   La variable est la variable de contrôle de boucle pour un **pour** boucle qui suit immédiatement un **pour** ou **parallèles pour** la directive et la référence variable apparaît à l’intérieur de la boucle .  
  
 Spécification d’une variable sur une **firstprivate**, **lastprivate**, ou **réduction** clause d’une directive entre provoque une référence implicite à la variable dans la forme contexte. De telles références implicites sont également soumises à la configuration requise ci-dessus.  
  
 Un seul **par défaut** clause peut être spécifiée sur un **parallèles** directive.  
  
 Attributs de partage de données peut être remplacée à l’aide de la valeur par défaut d’une variable le **privé**, **firstprivate**, **lastprivate**, **réduction**, et **partagé** clauses, comme illustré dans l’exemple suivant :  
  
```  
#pragma  omp  parallel  for  default(shared)  firstprivate(i)\  
   private(x)  private(r)  lastprivate(i)  
```