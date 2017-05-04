---
title: "Exception::HResult (propri&#233;t&#233;) | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::Exception::HResult"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Exception::HResult (propriété)"
ms.assetid: 24ef008d-6884-4b8b-9556-41bfa6e1edf1
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Exception::HResult (propri&#233;t&#233;)
HRESULT qui correspond à l'exception.  
  
## Syntaxe  
  
```cpp  
public:property int HResult {    int get();}  
```  
  
## Valeur de propriété  
 Valeur HRESULT.  
  
## Notes  
 La plupart des exceptions démarrent sous forme d'erreurs COM, qui sont retournées en tant que valeurs HRESULT. C\+\+\/CX convertit ces valeurs en objets Platform::Exception^, et cette propriété stocke la valeur du code d'erreur d'origine.  
  
## Configuration requise  
 **Client minimum pris en charge :** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **Serveur minimum pris en charge :** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **Espace de noms :** Platform  
  
 **Métadonnées :** platform.winmd  
  
## Voir aussi  
 [Platform::Exception \(classe\)](../cppcx/platform-exception-class.md)