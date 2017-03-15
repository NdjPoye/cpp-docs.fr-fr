---
title: "Erreur du compilateur C3199 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3199"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3199"
ms.assetid: e7a478d3-115a-40a3-991b-c7454fd2e28e
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Erreur du compilateur C3199
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

utilisation non valide des pragmas à virgule flottante : les exceptions ne sont pas prises en charge en mode sans précision  
  
 Le pragma [float\_control](../../preprocessor/float-control.md) a été utilisé pour spécifier le modèle d'exception à virgule flottante sous un paramètre [\/fp](../../build/reference/fp-specify-floating-point-behavior.md) autre que **\/fp:precise**.  
  
 L'exemple suivant génère l'erreur C3199 :  
  
```  
// C3199.cpp  
// compile with: /fp:fast  
#pragma float_control(except, on)   // C3199  
```