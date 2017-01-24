---
title: "marshal_context::~marshal_context | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "marshal_context::~marshal_context"
  - "msclr.interop.marshal_context.~marshal_context"
  - "marshal_context.~marshal_context"
  - "msclr::interop::marshal_context::~marshal_context"
  - "~marshal_context"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "marshal_context (classe) (C++), opérations"
ms.assetid: 34c41b38-4c33-4f61-b74e-831ac46b4ab5
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# marshal_context::~marshal_context
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Détruit un objet `marshal_context`.  
  
## Syntaxe  
  
```  
~marshal_context();  
```  
  
## Notes  
 Certaines conversions de données requièrent un contexte de sérialisation.  Consultez [Vue d'ensemble du marshaling dans C\+\+](../dotnet/overview-of-marshaling-in-cpp.md) pour plus d'informations sur les traductions qui requièrent un contexte et sur le fichier de sérialisation à inclure dans votre application.  
  
 La suppression d'un objet `marshal_context` invalidera des données converties par ce contexte.  Si vous souhaitez conserver les données lorsqu'un objet `marshal_context` est détruit, vous devez manuellement copier les données vers une variable qui persistera.  
  
## Configuration requise  
 **Fichier d'en\-tête :** \<msclr\\marshal.h\>, \<msclr\\marshal\_windows.h\>, \<msclr\\marshal\_cppstd.h\> ou \<msclr\\marshal\_atl.h\>  
  
 **Espace de noms :** msclr::interop  
  
## Voir aussi  
 [Vue d'ensemble du marshaling dans C\+\+](../dotnet/overview-of-marshaling-in-cpp.md)   
 [marshal\_as](../dotnet/marshal-as.md)   
 [marshal\_context, classe](../dotnet/marshal-context-class.md)