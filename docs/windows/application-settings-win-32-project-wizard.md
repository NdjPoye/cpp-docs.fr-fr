---
title: "Param&#232;tres de l&#39;application, Assistant Projet&#160;Win 32 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.appwiz.win32.appset"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "paramètres d'application (C++)"
  - "Assistant Projet Win32, paramètres de l’application"
ms.assetid: d6b818f0-9b23-4793-a6c5-df1c8c594bad
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# Param&#232;tres de l&#39;application, Assistant Projet&#160;Win 32
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Utilisez la page Paramètres de l'application de l'Assistant pour définir les options du projet Win32.  
  
 **Type d'application**  
 Crée le type d'application spécifié.  
  
|Option|Description|  
|------------|-----------------|  
|**Application console**|Crée une application console.  Les programmes de console sont développés à l'aide des [Console Functions](https://msdn.microsoft.com/en-us/library/ms813137.aspx) qui fournissent une prise en charge du mode caractères dans les fenêtres de console.  Les [bibliothèques runtime](../c-runtime-library/c-run-time-library-reference.md) Visual C\+\+ fournissent également des entrée et sortie à partir des fenêtres de console avec des fonctions d'E\/S standard, telles que **printf\_s\(\)** et **scanf\_s\(\)**.  Une application console est dépourvue d'interface graphique utilisateur.  Elle est compilée dans un fichier .exe et peut être exécutée en tant qu'application autonome à partir de la ligne de commande.<br /><br /> Vous pouvez ajouter une prise en charge des MFC et une prise en charge ATL à une application console.|  
|**Application Windows**|Crée un programme Win32.  Un programme Win32 est une application exécutable \(EXE\) écrite en C ou C\+\+ qui utilise des appels à l'API Win32 pour créer une interface graphique utilisateur.<br /><br /> Vous ne pouvez pas ajouter de prise en charge des MFC ou de prise en charge ATL à une application Windows.|  
|**DLL**|Crée une bibliothèque de liens dynamiques \(DLL\) Win32.  Une DLL Win32 est un fichier binaire écrit en C ou C\+\+, qui utilise des appels à l'API Win32 plutôt qu'à des classes MFC et qui joue le rôle d'une bibliothèque partagée de fonctions pouvant être utilisée simultanément par plusieurs applications.<br /><br /> Vous ne pouvez pas ajouter de prise en charge des MFC ou de prise en charge ATL à une application DLL.  Vous pouvez indiquer que la DLL exporte des symboles.|  
|**Bibliothèque statique**|Crée une bibliothèque statique.  Une bibliothèque statique est un fichier qui contient des objets ainsi que leurs fonctions et leurs données, et qui est lié à votre programme lors de la génération du fichier exécutable.  Cette rubrique explique comment créer les fichiers de départ et les [propriétés du projet](../ide/property-pages-visual-cpp.md) pour une bibliothèque statique.  Un fichier bibliothèque statique présente les avantages suivants :<br /><br /> -   Une bibliothèque statique Win32 est utile si l'application sur laquelle vous travaillez effectue des appels à l'API Win32 plutôt qu'à des classes MFC.<br />-   Le processus de liaison est le même, que le reste de votre application Windows soit écrit en C ou en C\+\+.<br />-   Vous pouvez lier une bibliothèque statique à un programme MFC ou non\-MFC.|  
  
 **Options supplémentaires**  
 Définit la prise en charge et les options pour l'application, en fonction de son type.  
  
|Option|Description|  
|------------|-----------------|  
|**Projet vide**|Spécifie que les fichiers projet sont vides.  Si vous avez un ensemble de fichiers de code source \(tels que des fichiers .cpp, des fichiers d'en\-tête, des icônes, des barres d'outils, des boîtes de dialogue, etc.\) et que vous voulez créer un projet dans l'environnement de développement Visual C\+\+, vous devez tout d'abord créer un projet vide, puis y ajouter les fichiers.<br /><br /> Cette sélection n'est pas disponible pour les projets de bibliothèque statique.|  
|**Exporter des symboles**|Spécifie que le projet de DLL exporte des symboles.|  
|**Fichier d'en\-tête précompilé**|Spécifie que le projet de bibliothèque statique utilise un fichier d'en\-tête précompilé.|  
|Vérifications SDL \(Security Development Lifecycle\)|Pour plus d'informations concernant SDL, consultez [Microsoft Security Development Lifecycle \(SDL\)  Process Guidance](84aed186-1d75-4366-8e61-8d258746bopq)|  
  
 **Ajouter la prise en charge de**  
 Permet d'ajouter une prise en charge pour une des bibliothèques fournies dans Visual C\+\+.  
  
|Option|Description|  
|------------|-----------------|  
|**ATL**|Intègre dans le projet une prise en charge pour les classes contenues dans la bibliothèque ATL \(Active Template Library\).  Cette option est uniquement destinée aux applications console Win32.<br /><br /> **Remarque** Cette option n'indique pas de prise en charge pour l'ajout d'objets ATL à l'aide des Assistants Code ATL.  Vous ne pouvez ajouter des objets ATL qu'aux projets ATL ou MFC disposant d'une prise en charge ATL.|  
|**MFC**|Intègre dans le projet une prise en charge pour la bibliothèque MFC \(Microsoft Foundation Class\).  Cette option est uniquement destinée aux applications console Win32 et aux bibliothèques statiques.|  
  
## Voir aussi  
 [Application Win32 \(Assistant\)](../windows/win32-application-wizard.md)   
 [Comment : créer une application de bureau Windows](../Topic/How%20to:%20Create%20a%20Windows%20Desktop%20Application.md)