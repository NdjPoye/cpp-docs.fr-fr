---
title: "Agile::GetAddressOfForInOut, m&#233;thode | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "agile/Platform::Agile::GetAddressOfForInOut"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform::Agile::GetAddressOfForInOut"
ms.assetid: 8bb27b4c-c325-49ee-91db-9adf87c530c4
caps.latest.revision: 2
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Agile::GetAddressOfForInOut, m&#233;thode
Retourne l'adresse d'un handle vers l'objet représenté par l'objet Agile actif.  
  
## Syntaxe  
  
```cpp  
  
       T^* GetAddressOfForInOut()   
throw();  
  
```  
  
#### Paramètres  
 `T`  
 Type spécifié par le paramètre de nom de type de modèle.  
  
## Valeur de retour  
 Adresse d'un handle vers l'objet représenté par l'objet Agile actif.  
  
## Notes  
 Cette opération acquiert le contexte de thread actuel et retourne l'adresse d'un handle vers l'objet sous\-jacent.  
  
## Configuration requise  
 **Client minimum pris en charge :** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **Serveur minimum pris en charge :** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **Espace de noms :** Platform  
  
 **En\-tête** : vccorlib.h  
  
## Voir aussi  
 [Platform::Agile, classe](../cppcx/platform-agile-class.md)