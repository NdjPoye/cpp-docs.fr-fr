---
title: "uuid (C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "uuid"
  - "uuid_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__declspec (mot clé) (C++), uuid"
  - "uuid __declspec (mot clé)"
ms.assetid: 9d004621-09bc-4a8d-871b-648f5d5102d7
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# uuid (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Section spécifique à Microsoft**  
  
 Le compilateur attache un GUID à une classe ou à une structure déclarée ou définie \(définitions complètes d'objet COM uniquement\) avec l'attribut `uuid`.  
  
## Syntaxe  
  
```  
  
__declspec( uuid("  
ComObjectGUID  
") ) declarator  
```  
  
## Notes  
 L'attribut `uuid` prend une chaîne comme argument.  Cette chaîne attribut un nom à un GUID dans un format normal de Registre avec ou sans les séparateurs **{ }**.  Par exemple :  
  
```  
struct __declspec(uuid("00000000-0000-0000-c000-000000000046")) IUnknown;  
struct __declspec(uuid("{00020400-0000-0000-c000-000000000046}")) IDispatch;  
```  
  
 Cet attribut peut être appliqué dans une redéclaration.  Cela permet aux en\-têtes systèmes de fournir les définitions des interfaces telles que **IUnknown** et la redéclaration dans un autre en\-tête \(par exemple COMDEF.H\) pour fournir un GUID.  
  
 Le mot clé [\_\_uuidof](../cpp/uuidof-operator.md) peut être appliqué pour récupérer le GUID constant attaché à un type défini par l'utilisateur.  
  
 **FIN de la section spécifique à Microsoft**  
  
## Voir aussi  
 [\_\_declspec](../cpp/declspec.md)   
 [Mots clés C\+\+](../cpp/keywords-cpp.md)