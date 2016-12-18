---
title: "Op&#233;rateurs de cast | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "opérateurs de cast"
  - "opérateurs (C++), cast"
  - "casts de type, opérateurs"
  - "conversion de type, opérateurs de cast"
ms.assetid: 43b90bbd-39ef-43e6-ae5d-e8a67a01de40
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Op&#233;rateurs de cast
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Un cast de type fournit une méthode pour la conversion explicite du type d'un objet dans une situation spécifique.  
  
## Syntaxe  
 *cast\-expression* :  
 *unary\-expression*  
  
 **\(**  *type\-name*  **\)**  *cast\-expression*  
  
 Le compilateur traite *cast\-expression* comme le type *type\-name* après la réalisation d'un cast de type.  Les casts peuvent être utilisés pour convertir des objets de tout type scalaire vers ou depuis tout autre type scalaire.  Les casts de types explicites sont contraints par les mêmes règles qui déterminent les effets des conversions implicites, présentées dans [Conversions d'assignation](../c-language/assignment-conversions.md).  Les restrictions supplémentaires sur les casts peuvent résulter des tailles réelles ou de la représentation des types spécifiques.  Consultez [Stockage des types de base](../c-language/storage-of-basic-types.md) pour obtenir plus d'informations sur les tailles réelles des types intégraux.  Pour plus d'informations sur les casts de type, consultez [Conversions de cast de type](../c-language/type-cast-conversions.md).  
  
## Voir aussi  
 [Opérateur de cast : \(\)](../cpp/cast-operator-parens.md)