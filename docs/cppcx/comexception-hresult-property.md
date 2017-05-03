---
title: "COMException::HResult (propri&#233;t&#233;) | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::COMException::HResult"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COMException::HResult (propriété)"
ms.assetid: 53762ab5-ce71-4397-b7b4-8175741c838f
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# COMException::HResult (propri&#233;t&#233;)
HRESULT qui correspond à l'exception.  
  
## Syntaxe  
  
```cpp  
public:property int HResult {    int get();}  
```  
  
## Valeur de propriété  
 Valeur HRESULT qui spécifie l'erreur.  
  
## Notes  
 Pour plus d’informations sur la façon d’interpréter la valeur HRESULT, consultez [Structure of COM Error Codes](http://go.microsoft.com/fwlink/p/?LinkId=262045).  
  
## Configuration requise  
 **Client minimum pris en charge :** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **Serveur minimum pris en charge :** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **Espace de noms :** Platform  
  
 **En\-tête** : vccorlib.h  
  
## Titre de la sous\-section  
  
## Voir aussi  
 [Platform::COMException \(classe\)](../cppcx/platform-comexception-class.md)