---
title: "Agile::operator-&gt;, op&#233;rateur | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "agile/Platform::Agile::operator->"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform::Agile::operator->"
ms.assetid: 570f4b0b-1735-49b3-8a30-4a302ac57074
caps.latest.revision: 2
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Agile::operator-&gt;, op&#233;rateur
Récupère un handle vers l’objet représenté par l’objet Agile actif.  
  
## Syntaxe  
  
```cpp  
  
       T^ operator->()   
const throw();  
```  
  
## Valeur de retour  
 Handle vers l’objet représenté par l’objet Agile actif.  
  
 Cet opérateur retourne un type interne non divulgué. Un moyen pratique de contenir la valeur de retour consiste à l’assigner à une variable déclarée avec le mot clé de déduction de type [auto](~/cpp/auto-cpp.md).  
  
## Configuration requise  
 **Client minimum pris en charge :** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **Serveur minimum pris en charge :** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **Espace de noms :** Platform  
  
 **En\-tête** : vccorlib.h  
  
## Voir aussi  
 [Platform::Agile, classe](../cppcx/platform-agile-class.md)