---
title: "marshal_context::marshal_context | Microsoft Docs"
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
  - "msclr::interop::marshal_context::marshal_context"
  - "marshal_context::marshal_context"
  - "msclr.interop.marshal_context.marshal_context"
  - "marshal_context.marshal_context"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "marshal_context (classe) (C++), opérations"
ms.assetid: 5f08c895-60b0-4f72-97ff-7ae37c68e853
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# marshal_context::marshal_context
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Construit un objet `marshal_context` à utiliser pour la conversion de données entre les types de données managés et natifs.  
  
## Syntaxe  
  
```  
marshal_context();  
```  
  
## Notes  
 Certaines conversions de données requièrent un contexte de sérialisation.  Consultez [Vue d'ensemble du marshaling dans C\+\+](../dotnet/overview-of-marshaling-in-cpp.md) pour plus d'informations sur les traductions qui requièrent un contexte et sur le fichier de sérialisation à inclure dans votre application.  
  
## Exemple  
 Consultez l'exemple pour [marshal\_context::marshal\_as](../dotnet/marshal-context-marshal-as.md).  
  
## Configuration requise  
 **Fichier d'en\-tête :** \<msclr\\marshal.h\>, \<msclr\\marshal\_windows.h\>, \<msclr\\marshal\_cppstd.h\> ou \<msclr\\marshal\_atl.h\>  
  
 **Espace de noms :** msclr::interop  
  
## Voir aussi  
 [Vue d'ensemble du marshaling dans C\+\+](../dotnet/overview-of-marshaling-in-cpp.md)   
 [marshal\_as](../dotnet/marshal-as.md)   
 [marshal\_context, classe](../dotnet/marshal-context-class.md)