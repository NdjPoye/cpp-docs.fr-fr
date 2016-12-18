---
title: "DontUseNewUseMake, classe | Microsoft Docs"
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
  - "implements/Microsoft::WRL::Details::DontUseNewUseMake"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DontUseNewUseMake (classe)"
ms.assetid: 8b38d07b-fc14-4cea-afb9-4c1a7dde0093
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# DontUseNewUseMake, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Prend en charge l'infrastructure WRL et n'est pas destiné à être utilisé directement à partir de votre code.  
  
## Syntaxe  
  
```  
class DontUseNewUseMake;  
```  
  
## Notes  
 Empêche l'utilisation de l'opérateur `new` dans RuntimeClass.  Par conséquent, vous devez plutôt utiliser [la fonction Make](../windows/make-function.md).  
  
## Membres  
  
### Opérateurs publics  
  
|Name|Description|  
|----------|-----------------|  
|[DontUseNewUseMake::operator new, opérateur](../windows/dontusenewusemake-operator-new-operator.md)|Surcharge l'opérateur `new` et l'empêche d'être utilisée dans RuntimeClass.|  
  
## Hiérarchie d'héritage  
 `DontUseNewUseMake`  
  
## Configuration requise  
 **En\-tête:** implements.h  
  
 **Espace de noms:** Microsoft::WRL::Details  
  
## Voir aussi  
 [Microsoft::WRL::Details, espace de noms](../windows/microsoft-wrl-details-namespace.md)   
 [Make, fonction](../windows/make-function.md)