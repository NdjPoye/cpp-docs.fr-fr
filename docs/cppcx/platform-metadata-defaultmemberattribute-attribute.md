---
title: "Platform::Metadata::DefaultMemberAttribute (attribut) | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::Metadata::DefaultMemberAttribute"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform::Metadata::DefaultMemberAttribute (attribut)"
ms.assetid: d8abda01-c257-4371-aec4-541d4825e0af
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 4
---
# Platform::Metadata::DefaultMemberAttribute (attribut)
Indique la fonction par défaut à appeler parmi plusieurs fonctions surchargées possibles.  
  
## Syntaxe  
  
```cpp  
  
public ref class DefaultMember abstract : Attribute  
```  
  
## Héritage  
 [Platform::Object](../cppcx/object-object-constructor.md)  
  
 [Platform::Metadata::Attribute](../cppcx/platform-metadata-attribute-attribute.md)  
  
## Notes  
 Appliquez l'attribut DefaultMember à une méthode qui est consommée par une application JavaScript.  
  
## Configuration requise  
 **Client minimum pris en charge :** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **Serveur minimum pris en charge :** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **Espace de noms :** Platform::Metadata  
  
 **Métadonnées :** platform.winmd  
  
## Voir aussi  
 [Platform::Metadata \(espace de noms\)](../cppcx/platform-metadata-namespace.md)