---
title: "Exceptions mat&#233;rielles | Microsoft Docs"
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
  - "erreurs (C++), matériel"
  - "erreurs (C++), niveau bas"
  - "exceptions, matériel"
  - "exceptions matérielles"
  - "erreurs de niveau bas"
ms.assetid: 06ac6f01-a8cf-4426-bb12-1688315ae1cd
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Exceptions mat&#233;rielles
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La plupart des exceptions standard identifiées par le système d'exploitation sont des exceptions définies par le matériel.  Windows identifie quelques exceptions logicielles de bas niveau, mais celles\-ci sont généralement gérées de façon optimale par le système d'exploitation.  
  
 Windows mappe les erreurs matérielles des différents processeurs aux codes d'exception figurant dans cette section.  Dans certains cas, un processeur peut générer uniquement un sous\-ensemble de ces exceptions.  Windows prétraite les informations sur l'exception et émet le code d'exception approprié.  
  
 Les exceptions matérielles identifiées par Windows sont résumées dans le tableau suivant :  
  
|Code d'exception|Raison de l'exception|  
|----------------------|---------------------------|  
|**STATUS\_ACCESS\_VIOLATION**|Lecture ou écriture à un emplacement mémoire inaccessible.|  
|**STATUS\_BREAKPOINT**|Rencontre d'un point d'arrêt défini par le matériel ; utilisé uniquement par les débogueurs.|  
|**STATUS\_DATATYPE\_MISALIGNMENT**|Lecture ou écriture dans les données à une adresse qui n'est pas correctement alignée ; par exemple, des entités 16 bits doivent être alignées sur des limites de 2 octets. \(Non applicable aux processeurs Intel 80*x*86.\)|  
|**STATUS\_FLOAT\_DIVIDE\_BY\_ZERO**|Division du type à virgule flottante par 0,0.|  
|**STATUS\_FLOAT\_OVERFLOW**|Dépassement de l'exposant positif maximal du type à virgule flottante.|  
|**STATUS\_FLOAT\_UNDERFLOW**|Dépassement de la grandeur de l'exposant négatif le plus bas du type à virgule flottante.|  
|**STATUS\_FLOATING\_RESEVERED\_OPERAND**|Utilisation d'un format à virgule flottante réservé \(utilisation non valide de format\).|  
|**STATUS\_ILLEGAL\_INSTRUCTION**|Tentative d'exécution d'un code d'instruction non défini par le processeur.|  
|**STATUS\_PRIVILEGED\_INSTRUCTION**|Exécution d'une instruction non autorisée dans le mode actuel de l'ordinateur.|  
|**STATUS\_INTEGER\_DIVIDE\_BY\_ZERO**|Division d'un type entier par 0.|  
|**STATUS\_INTEGER\_OVERFLOW**|Tentative d'une opération qui dépasse la plage de l'entier.|  
|**STATUS\_SINGLE\_STEP**|Exécution d'une instruction en mode pas à pas ; utilisé uniquement par les débogueurs.|  
  
 Un grand nombre des exceptions répertoriées dans le tableau précédent sont destinées à être gérées par les débogueurs, le système d'exploitation ou un autre code de bas niveau.  À l'exception des erreurs relatives aux entiers et aux nombres à virgule flottante, votre code ne doit pas gérer ces erreurs.  Ainsi, vous devez généralement utiliser le filtre de gestion des exceptions pour ignorer les exceptions \(valeur 0\).  Sinon, vous risquez d'empêcher les mécanismes de niveau inférieur de réagir de manière appropriée.  Toutefois, vous pouvez prendre les précautions appropriées contre les conséquences possibles de ces erreurs de bas niveau en [écrivant des gestionnaires de terminaison](../cpp/writing-a-termination-handler.md).  
  
## Voir aussi  
 [Écriture d'un gestionnaire d'exceptions](../cpp/writing-an-exception-handler.md)   
 [Gestion structurée des exceptions](../cpp/structured-exception-handling-c-cpp.md)