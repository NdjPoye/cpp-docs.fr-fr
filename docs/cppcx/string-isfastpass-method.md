---
title: "String::IsFastPass, m&#233;thode | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::String::IsFastPass"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform::String::IsFastPass"
ms.assetid: 0a8c2db7-e44f-45fe-9570-3dc82fbbacdd
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# String::IsFastPass, m&#233;thode
Indique si l'objet String actuel participe à une opération de *passage rapide*. Dans une opération de passage rapide, le comptage des références est interrompu.  
  
## Syntaxe  
  
```cpp  
  
bool IsFastPass();  
```  
  
## Valeur de retour  
 `true` si l'objet String actuel a fait l'objet d'un passage rapide ; sinon, `false`.  
  
## Notes  
 Au cours d'un appel de fonction où un objet, dont les références sont comptabilisées, constitue un paramètre, et que la fonction appelée ne lit que cet objet, le compilateur peut sans risque interrompre le décompte de références et améliorer les performances d'appel. Votre code ne peut rien faire d'utile avec cette propriété. Le système gère tous les détails.  
  
## Configuration requise  
 **Client minimum pris en charge :** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **Serveur minimum pris en charge :** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **Espace de noms :** Platform  
  
 **Métadonnées :** vccorlib.h  
  
## Voir aussi  
 [Platform::String, classe](../cppcx/platform-string-class.md)