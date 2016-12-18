---
title: "Classes du support COM du compilateur | Microsoft Docs"
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
  - "_com_raise_error"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "compilateur cl.exe, prise en charge COM"
  - "COM, prise en charge par le compilateur"
ms.assetid: 6d800d9b-b902-4033-9639-740a30b06f88
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Classes du support COM du compilateur
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Section spécifique à Microsoft**  
  
 Les classes standard sont utilisées pour prendre en charge certains types COM.  Les classes sont définies dans comdef.h et les fichiers d'en\-tête sont générés à partir de la bibliothèque de types.  
  
|Classe|Objectif|  
|------------|--------------|  
|[\_bstr\_t](../cpp/bstr-t-class.md)|Encapsule le type `BSTR` pour fournir des opérateurs et des méthodes utiles.|  
|[\_com\_error](../cpp/com-error-class.md)|Définit l'objet d'erreur levé par [\_com\_raise\_error](../cpp/com-raise-error.md) dans la plupart des échecs.|  
|[\_com\_ptr\_t](../cpp/com-ptr-t-class.md)|Encapsule des pointeurs d'interface COM et automatise les appels requis à `AddRef`, **Release** et `QueryInterface`.|  
|[\_variant\_t](../cpp/variant-t-class.md)|Encapsule le type **VARIANT** pour fournir des opérateurs et des méthodes utiles.|  
  
## FIN de la section spécifique à Microsoft  
  
## Voir aussi  
 [Prise en charge COM du compilateur](../cpp/compiler-com-support.md)   
 [Fonctions globales COM du compilateur](../cpp/compiler-com-global-functions.md)   
 [Référence du langage C\+\+](../cpp/cpp-language-reference.md)