---
title: "Agile::GetAddressOf, m&#233;thode | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "agile/Platform::Agile::GetAddressOf"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform::Agile::GetAddressOf"
ms.assetid: f015edf9-4155-4992-a6fc-7ff1edcc5d1e
caps.latest.revision: 2
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Agile::GetAddressOf, m&#233;thode
Réinitialise l’objet Agile actif, puis retourne l’adresse d’un handle vers un objet de type `T`.  
  
## Syntaxe  
  
```cpp  
  
       T^* GetAddressOf()   
throw();  
```  
  
#### Paramètres  
 `T`  
 Type spécifié par le paramètre de nom de type de modèle.  
  
## Valeur de retour  
 Adresse d’un handle vers un objet de type `T`.  
  
## Notes  
 Cette opération libère la représentation actuelle d’un objet de type `T`, le cas échéant, réinitialise les membres de données de l’objet Agile, acquiert le contexte de thread actuel, puis retourne l’adresse d’une variable handle\-to\-object qui peut représenter un objet non agile. Pour qu’une instance de la classe Agile représente un objet, utilisez l’opérateur d’assignation \([Agile::operator\=](../cppcx/agile-operator-assign-operator.md)\) pour assigner l’objet à l’instance de la classe Agile.  
  
## Configuration requise  
 **Client minimum pris en charge :** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **Serveur minimum pris en charge :** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **Espace de noms :** Platform  
  
 **En\-tête** : vccorlib.h  
  
## Voir aussi  
 [Platform::Agile, classe](../cppcx/platform-agile-class.md)