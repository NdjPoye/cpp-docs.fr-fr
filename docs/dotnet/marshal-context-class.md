---
title: "marshal_context, classe | Microsoft Docs"
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
  - "marshal_context"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "marshal_context (classe) (C++)"
ms.assetid: 241b0cf6-4ca4-4812-aaee-d671c11dc034
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# marshal_context, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Cette classe convertit les données entre les environnements natifs et les environnements managés.  
  
## Syntaxe  
  
```  
class marshal_context  
```  
  
## Notes  
 Utilisez la classe d' `marshal_context` pour des conversions de données qui requièrent un contexte.  Consultez [Vue d'ensemble du marshaling dans C\+\+](../dotnet/overview-of-marshaling-in-cpp.md) pour plus d'informations à propos des conversions qui requièrent un contexte et à propos du fichier de marshaling qui doit être inclus.  Le résultat du marshaling lorsque vous utilisez un contexte est valide uniquement tant que l'objet d' `marshal_context` est détruit.  Pour conserver le résultat, vous devez copier les données.  
  
 Le même `marshal_context` peut être utilisé pour plusieurs conversions de données.  Réutiliser le contexte de cette manière n'affecte pas les résultats des appels précédents de marshaling.  
  
## Configuration requise  
 **Fichier d'en\-tête :** \<msclr\\marshal.h\>, \<msclr\\marshal\_windows.h\>, \<msclr\\marshal\_cppstd.h\> ou \<msclr\\marshal\_atl.h\>  
  
 **Espace de noms :** msclr::interop  
  
## Voir aussi  
 [Vue d'ensemble du marshaling dans C\+\+](../dotnet/overview-of-marshaling-in-cpp.md)   
 [marshal\_as](../dotnet/marshal-as.md)