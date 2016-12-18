---
title: "Varargs | Microsoft Docs"
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
ms.assetid: aac0c54b-0a2d-4a22-b1de-ee41381a3eb1
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Varargs
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Si les paramètres sont passés par l'intermédiaire de varargs \(par exemple, d'arguments de points de suspension\), le passage de paramètres normal s'applique essentiellement, notamment le fait de répandre le cinquième argument et les suivants.  C'est à nouveau l'appelé qui est chargé de faire un dump des arguments dont l'adresse est prise.  Pour les valeurs à virgule flottante uniquement, le registre entier et le registre à virgule flottante contiendront la valeur float si l'appelé attend cette valeur dans les registres entiers.  
  
## Voir aussi  
 [Convention d'appel](../build/calling-convention.md)