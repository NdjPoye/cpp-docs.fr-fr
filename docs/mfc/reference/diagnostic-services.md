---
title: "Services de diagnostic | Microsoft Docs"
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
  - "vc.mfc.macros"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "diagnostic, diagnostic (fonctions et variables)"
  - "diagnostic, diagnostic (services)"
  - "diagnostic, liste des MFC générales"
  - "diagnostic (fonctions et variables)"
  - "diagnostic (macros)"
  - "diagnostic (macros), liste des MFC générales"
  - "diagnostic (services)"
  - "diagnostics, diagnostic (fonctions et variables)"
  - "diagnostics, diagnostic (services)"
  - "diagnostics, liste des MFC générales"
  - "diagnostic général (fonctions et variables)"
  - "diagnostic général (macros dans MFC)"
  - "MFC, diagnostic (services)"
  - "diagnostic d'objet (fonctions dans MFC)"
  - "services, diagnostic"
ms.assetid: 8d78454f-9fae-49c2-88c9-d3fabd5393e8
caps.latest.revision: 20
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Services de diagnostic
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

La bibliothèque Microsoft Foundation Class fournit de nombreux services de diagnostic qui simplifient le débogage de vos programmes. Elle propose notamment des macros et des fonctions globales qui vous permettent d’effectuer le suivi des allocations mémoire de votre programme, de vider le contenu des objets au moment de l’exécution et d’afficher des messages de débogage au moment de l’exécution. Les macros et les fonctions globales pour les services de diagnostic sont regroupées dans les catégories suivantes :  
  
-   Macros de diagnostic général  
  
-   Fonctions et variables de diagnostic général  
  
-   Fonctions de diagnostic d’objet  
  
 Ces macros et fonctions sont disponibles pour toutes les classes dérivées de `CObject` dans les versions Debug et Release de MFC. Toutefois, seules `DEBUG_NEW` et **VERIFY** ont un effet dans la version Release.  
  
 Dans la bibliothèque Debug, tous les blocs de mémoire alloués sont entourés d’une série d’« octets de protection ». Si ces octets sont perturbés par une écriture en mémoire non contrôlée, les routines de diagnostic peuvent signaler un problème. Si vous incluez la ligne :  
  
 [!code-cpp[NVC_MFCCObjectSample#14](../../mfc/codesnippet/CPP/diagnostic-services_1.cpp)]  
  
 dans votre fichier d’implémentation, tous les appels à **new** stockent le nom de fichier et le numéro de ligne où l’allocation de mémoire a eu lieu. La fonction [CMemoryState::DumpAllObjectsSince](../Topic/CMemoryState::DumpAllObjectsSince.md) affiche ces informations supplémentaires, ce qui vous permet d’identifier les fuites de mémoire. Pour plus d’informations sur la sortie de diagnostic, consultez également la classe [CDumpContext](../../mfc/reference/cdumpcontext-class.md).  
  
 La bibliothèque Runtime C prend également en charge un ensemble de fonctions de diagnostic que vous pouvez utiliser pour déboguer vos applications. Pour plus d’informations, consultez [Routines de débogage](../../c-runtime-library/debug-routines.md) dans la Référence de la bibliothèque runtime.  
  
### Macros de diagnostic général MFC  
  
|||  
|-|-|  
|[ASSERT](../Topic/ASSERT%20\(MFC\).md)|Affiche un message et interrompt le programme si l’expression spécifiée donne la valeur **FALSE** dans la version Debug de la bibliothèque.|  
|[ASSERT\_KINDOF](../Topic/ASSERT_KINDOF.md)|Vérifie qu’un objet est un objet de la classe spécifiée ou d’une classe dérivée de la classe spécifiée.|  
|[ASSERT\_VALID](../Topic/ASSERT_VALID.md)|Teste la validité interne d’un objet en appelant sa fonction membre `AssertValid` ; généralement substituée à partir de `CObject`.|  
|[DEBUG\_NEW](../Topic/DEBUG_NEW.md)|Fournit un nom de fichier et un numéro de ligne pour toutes les allocations d’objets en mode débogage, pour faciliter la recherche des fuites de mémoire.|  
|[DEBUG\_ONLY](../Topic/DEBUG_ONLY.md)|Semblable à **ASSERT**, mais ne teste pas la valeur de l’expression. Utile pour le code qui doit s’exécuter uniquement en mode débogage.|  
|[TRACE](../Topic/TRACE.md)|Fournit des fonctionnalités semblables à `printf` dans la version Debug de la bibliothèque.|  
|[VERIFY](../Topic/VERIFY.md)|Semblable à **ASSERT**, mais évalue l’expression dans la versions Release et Debug de la bibliothèque.|  
  
### Fonctions et variables de diagnostic général MFC  
  
|||  
|-|-|  
|[afxDump](../Topic/afxDump%20\(CDumpContext%20in%20MFC\).md)|Variable globale qui envoie des informations [CDumpContext](../../mfc/reference/cdumpcontext-class.md) à la fenêtre de sortie du débogueur ou au terminal de débogage.|  
|[afxMemDF](../Topic/afxMemDF.md)|Variable globale qui contrôle le comportement de l’allocateur de mémoire de débogage.|  
|[AfxCheckError](../Topic/AfxCheckError.md)|Variable globale qui sert à tester le **SCODE** passé pour voir s’il s’agit d’une erreur et, si c’est le cas, génère l’erreur appropriée.|  
|[AfxCheckMemory](../Topic/AfxCheckMemory.md)|Vérifie l’intégrité de toute la mémoire allouée actuellement.|  
|[AfxDump](../Topic/AfxDump%20\(MFC\).md)|En cas d’appel dans le débogueur, vide l’état d’un objet pendant le débogage.|  
|[AfxDumpStack](../Topic/AfxDumpStack.md)|Génère une image de la pile actuelle. Cette fonction est toujours liée de manière statique.|  
|[AfxEnableMemoryLeakDump](../Topic/AfxEnableMemoryLeakDump.md)|Active le vidage de fuite de mémoire.|  
|[AfxEnableMemoryTracking](../Topic/AfxEnableMemoryTracking.md)|Active et désactive le suivi de la mémoire.|  
|[AfxIsMemoryBlock](../Topic/AfxIsMemoryBlock.md)|Vérifie qu’un bloc de mémoire a été alloué correctement.|  
|[AfxIsValidAddress](../Topic/AfxIsValidAddress.md)|Vérifie qu’une plage d’adresses mémoire est dans les limites du programme.|  
|[AfxIsValidString](../Topic/AfxIsValidString.md)|Détermine si un pointeur vers une chaîne est valide.|  
|[AfxSetAllocHook](../Topic/AfxSetAllocHook.md)|Permet l’appel d’une fonction lors de chaque allocation de mémoire.|  
  
### Fonctions de diagnostic d’objet MFC  
  
|||  
|-|-|  
|[AfxDoForAllClasses](../Topic/AfxDoForAllClasses.md)|Exécute une fonction spécifiée sur toutes les classes dérivées de `CObject` qui prennent en charge la vérification du type au moment de l’exécution.|  
|[AfxDoForAllObjects](../Topic/AfxDoForAllObjects.md)|Exécute une fonction spécifiée sur tous les objets dérivés de `CObject` qui ont été alloués avec **new**.|  
  
## Voir aussi  
 [Macros et objet Globals](../../mfc/reference/mfc-macros-and-globals.md)