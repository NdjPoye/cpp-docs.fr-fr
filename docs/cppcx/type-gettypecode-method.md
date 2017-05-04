---
title: "Type::GetTypeCode Method | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::Type::GetTypeCode"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Type::GetTypeCode Method"
ms.assetid: 20c30432-91a3-400e-b9d6-eba265daaefc
caps.latest.revision: 3
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Type::GetTypeCode Method
Récupère une catégorie de type numérique de types intégrés.  
  
## Syntaxe  
  
```cpp  
Platform::TypeCode GetTypeCode();  
```  
  
## Valeur de retour  
 L’un des valeurs énumérées Platform::TypeCode.  
  
## Notes  
 L’équivalent de la méthode membre GetTypeCode\(\) est la propriété `typeid`.  
  
## Configuration requise  
 **Client minimum pris en charge :** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **Serveur minimum pris en charge :** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **Espace de noms :** Platform  
  
 **Métadonnées :** platform.winmd  
  
## Voir aussi  
 [Platform::ValueType \(classe\)](../cppcx/platform-valuetype-class.md)