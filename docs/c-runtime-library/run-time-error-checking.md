---
title: "V&#233;rifications des erreurs au moment de l&#39;ex&#233;cution | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "c.runtime"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "vérifications des erreurs au moment de l'exécution"
  - "erreurs d'exécution, vérifier"
ms.assetid: c965dd01-57ad-4a3c-b1d6-5aa04f920501
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# V&#233;rifications des erreurs au moment de l&#39;ex&#233;cution
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La bibliothèque Runtime C contient des fonctions qui prennent en charge les contrôles d'erreur d'exécution \(RTC\).  La vérification des erreurs d'exécution vous permet de générer votre programme de telle manière que certains types d'erreurs d'exécution soient rapportées.  Vous spécifiez la façon dont les erreurs sont signalées et lesquelles les sont.  Pour plus d'informations, consultez [Vérifications des erreurs à l'exécution](../Topic/How%20to:%20Use%20Native%20Run-Time%20Checks.md).  
  
 Utilisez les fonctions suivantes pour personnaliser la façon dont votre programme effetue la vérification des erreurs d'exécution.  
  
### Active les fonctions vérifiant les erreurs au moment de l'exécution.  
  
|Fonction|Utilisez|Équivalent de .NET Framework|  
|--------------|--------------|----------------------------------|  
|[\_RTC\_GetErrDesc](../c-runtime-library/reference/rtc-geterrdesc.md)|Retourne une brève description d'un type de contrôle d'erreur d'exécution.||  
|[\_RTC\_NumErrors](../c-runtime-library/reference/rtc-numerrors.md)|Retourne le nombre total d'erreurs détectés par les vérifications des erreurs au moment de l'exécution.||  
|[\_RTC\_SetErrorFunc](../c-runtime-library/reference/rtc-seterrorfunc.md)|Désigne une fonction comme gestionnaire pour stocker les logs des contrôles d'erreur d'exécution \(RTC\).||  
|[\_RTC\_SetErrorType](../c-runtime-library/reference/rtc-seterrortype.md)|Associe une erreur qui est identifiée par les contrôles d'erreur d'exécution avec un type.||  
  
## Voir aussi  
 [Routines runtime par catégorie](../c-runtime-library/run-time-routines-by-category.md)   
 [\/RTC \(Vérifications des erreurs au moment de l'exécution\)](../build/reference/rtc-run-time-error-checks.md)   
 [runtime\_checks](../preprocessor/runtime-checks.md)   
 [RTC sample](http://msdn.microsoft.com/fr-fr/b3415b09-f6fd-43dc-8c02-9a910bc2574e)   
 [Routines de débogage](../c-runtime-library/debug-routines.md)