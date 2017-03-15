---
title: "Fonctions globales&#160;COM du compilateur | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "compilateur cl.exe, prise en charge COM"
  - "COM, prise en charge par le compilateur"
ms.assetid: 74449d26-50a2-47c7-b175-7cf2cf83533e
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Fonctions globales&#160;COM du compilateur
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Section spécifique à Microsoft**  
  
 Les routines suivantes sont disponibles :  
  
|Fonction|Description|  
|--------------|-----------------|  
|[\_com\_raise\_error](../cpp/com-raise-error.md)|Lève [\_com\_error](../cpp/com-error-class.md) en réponse à un échec.|  
|[\_set\_com\_error\_handler](../cpp/set-com-error-handler.md)|Remplace la fonction par défaut utilisée pour la gestion des erreurs COM.|  
|[ConvertBSTRToString](../cpp/convertbstrtostring.md)|Convertit une valeur `BSTR` en **char \***.|  
|[ConvertStringToBSTR](../cpp/convertstringtobstr.md)|Convertit une valeur **char \*** en un `BSTR`.|  
  
## FIN de la section spécifique à Microsoft  
  
## Voir aussi  
 [Classes du support COM du compilateur](../cpp/compiler-com-support-classes.md)   
 [Prise en charge COM du compilateur](../cpp/compiler-com-support.md)