---
title: "Platform::ReCreateException, m&#233;thode | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::ReCreateException"
dev_langs: 
  - "C++"
ms.assetid: fa73d1ab-86e4-4d26-a7d9-81938c1c7e77
caps.latest.revision: 6
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 4
---
# Platform::ReCreateException, m&#233;thode
Cette méthode est destinée à un usage interne uniquement et n'est pas destinée au code utilisateur. Utilisez la [méthode Exception::CreateException](../cppcx/exception-createexception-method.md) à la place.  
  
## Syntaxe  
  
```vb  
static Exception^ ReCreateException(int hr)  
```  
  
#### Paramètres  
  
## Valeur de propriété\/valeur de retour  
 Retourne un nouvel objet Platform::Exception^, basé sur le HRESULT spécifié.  
  
## Équivalent .NET Framework  
  
## Configuration requise