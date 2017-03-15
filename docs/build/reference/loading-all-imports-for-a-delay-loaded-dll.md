---
title: "Chargement de toutes les importations pour une DLL &#224; chargement diff&#233;r&#233; | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__HrLoadAllImportsForDll (option de l'éditeur de liens)"
ms.assetid: 975fcd97-1a56-4a16-9698-e1a249d2d592
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Chargement de toutes les importations pour une DLL &#224; chargement diff&#233;r&#233;
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

La fonction **\_\_HrLoadAllImportsForDll**, définie dans delayhlp.cpp, indique à l'éditeur de liens de charger toutes les importations d'une DLL spécifiée avec l'option de l'éditeur de liens [\/delayload](../../build/reference/delayload-delay-load-import.md).  
  
 Le chargement de toutes les importations vous permet de placer la gestion des erreurs à un emplacement unique dans votre code et vous évite d'avoir à recourir à la gestion des erreurs concernant les appels effectifs vers les importations.  Vous évitez également une situation où votre application échoue partiellement pendant un processus, suite à une défaillance du code de la fonction d'assistance pour charger une importation.  
  
 L'appel de **\_\_HrLoadAllImportsForDll** ne modifie pas le comportement des raccordements et du traitement des erreurs ; pour plus d'informations, consultez [Gestion et notification des erreurs](../../build/reference/error-handling-and-notification.md).  
  
 Le nom de la DLL passé à **\_\_HrLoadAllImportsForDll** est comparé au nom enregistré à l'intérieur de la DLL elle\-même et respecte la casse.  
  
 L'exemple suivant montre comment appeler **\_\_HrLoadAllImportsForDll** :  
  
```  
if (FAILED(__HrLoadAllImportsForDll("delay1.dll"))) {  
   printf ( "failed on snap load, exiting\n" );  
   exit(2);  
}  
```  
  
## Voir aussi  
 [Prise en charge de l'éditeur de liens pour les DLL à chargement différé](../../build/reference/linker-support-for-delay-loaded-dlls.md)