---
title: "Using Replaceable Parameters (The Registrar&#39;s Preprocessor) | Microsoft Docs"
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
  - "AddReplacement"
  - "ClearReplacements"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "%MODULE%"
ms.assetid: 0b376994-84a6-4967-8d97-8c01dfc94efe
caps.latest.revision: 12
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Using Replaceable Parameters (The Registrar&#39;s Preprocessor)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les paramètres remplaçables permettent au client d'un registre pour spécifier les données à l'exécution.  Pour cela, le registre met à jour une table de remplacement dans laquelle il écrit les valeurs associées aux paramètres remplaçables dans votre script.  Le registre de ces entrées au moment de l'exécution.  
  
##  <a name="_atl_using_.25.module.25"></a> Utilisation %MODULE%  
 [L'Assistant Contrôle ATL](../atl/reference/atl-control-wizard.md) génère automatiquement un script qui utilise `%MODULE%`.  ATL utilise ce paramètre remplaçable pour l'emplacement réel de la DLL ou du fichier EXE de votre serveur.  
  
## Concaténer des données à l'exécution avec des données de script  
 Une autre utilisation du préprocesseur est de concaténer des données à l'exécution avec des données de script.  Par exemple, supposons qu'il a besoin d'une entrée qui contient un chemin d'accès complet à un module avec la chaîne « `, 1` » ajouté à la fin.  d'abord, définissez l'expansion suivante :  
  
```  
'MySampleKey' = s '%MODULE%, 1'  
```  
  
 Ensuite, avant d'appeler un script du traitement des méthodes répertoriées dans [appeler des scripts](../atl/invoking-scripts.md), ajoutez un remplacement au mappage :  
  
 [!code-cpp[NVC_ATL_Utilities#113](../atl/codesnippet/CPP/using-replaceable-parameters-the-registrar-s-preprocessor_1.cpp)]  
  
 Pendant l'analyse du script, le registre se développe `'%MODULE%, 1'` à `c:\mycode\mydll.dll, 1`.  
  
> [!NOTE]
>  Dans un script d'inscription, 4K est la taille maximale de jeton.  \(Le jeton d'Un est un élément reconnaissable dans la syntaxe.\) Cela inclut le créées ou développées par le préprocesseur.  
  
> [!NOTE]
>  Pour remplacer les valeurs de remplacement au moment de l'exécution, supprimez l'appel du script vers la macro de [DECLARE\_REGISTRY\_RESOURCE](../Topic/DECLARE_REGISTRY_RESOURCE.md) ou de [DECLARE\_REGISTRY\_RESOURCEID](../Topic/DECLARE_REGISTRY_RESOURCEID.md) .  À la place, remplacez \-le par votre propre méthode d' `UpdateRegistry` qui appelle [CAtlModule::UpdateRegistryFromResourceD](../Topic/CAtlModule::UpdateRegistryFromResourceD.md) ou [CAtlModule::UpdateRegistryFromResourceS](../Topic/CAtlModule::UpdateRegistryFromResourceS.md), et passez votre tableau de structures de **\_ATL\_REGMAP\_ENTRY** .  Votre matrice de **\_ATL\_REGMAP\_ENTRY** doit avoir au moins une entrée à laquelle est défini**NULLNULL**{,}, et cette entrée doit toujours être la dernière entrée.  Sinon, une erreur de violation d'accès est générée lorsque **UpdateRegistryFromResource** est appelé.  
  
> [!NOTE]
>  Lors de la génération d'un projet que les sorties un fichier exécutable, ATL ajoute automatiquement des guillemets autour de le nom de chemin d'accès qui l'a créé au moment de l'exécution avec le paramètre de script d'inscription de **%MODULE%** .  Si vous ne souhaitez pas que le chemin d'accès pour inclure des guillemets, utilisez le paramètre de **%MODULE\_RAW%** à la place.  
>   
>  Lors de la génération d'un projet que les sorties une DLL, ATL ajouteront ne pas de guillemets au chemin d'accès si **%MODULE%** ou **%MODULE\_RAW%** est utilisé.  
  
## Voir aussi  
 [Creating Registrar Scripts](../atl/creating-registrar-scripts.md)