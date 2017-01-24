---
title: "Cha&#238;nes mod&#232;les de document, Assistant Application MFC | Microsoft Docs"
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
  - "vc.appwiz.mfc.exe.doctemp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Assistant Application MFC, chaînes modèles de document"
ms.assetid: 8109f662-3182-4682-977a-2503321c678a
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Cha&#238;nes mod&#232;les de document, Assistant Application MFC
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Dans la page Chaînes modèles de document de l'Assistant Application MFC, vous indiquez ou précisez les options ci\-après pour faciliter la gestion et la localisation du document.  Les chaînes modèles de document sont disponibles pour les applications qui incluent la **Prise en charge de l'architecture Document\/Vue** dans la page [Type d'application](../../mfc/reference/application-type-mfc-application-wizard.md).  Elles ne sont pas disponibles pour les boîtes de dialogue.  Dans la mesure où la majorité des chaînes des modèles de document sont visibles et employées par les utilisateurs de l'application, elles sont traduites dans la **Langue des ressources** indiquée dans la page **Type d'application** de l'Assistant.  
  
 **Chaînes non localisées**  
 S'applique aux applications créant des documents utilisateur.  Les utilisateurs peuvent ouvrir, imprimer, et enregistrer les documents plus facilement si vous fournissez une extension de fichier et un ID de type de fichier.  Ces éléments ne sont pas traduits parce qu'ils sont utilisés par le système, et non pas par l'utilisateur.  
  
|Option|Description|  
|------------|-----------------|  
|**Extension du fichier**|Définit l'extension de fichier associée aux documents que l'utilisateur enregistre lors de l'utilisation de l'application.  Par exemple, si votre projet est nommé Widget, vous pouvez nommer l'extension de fichier .wgt. \(Lorsque vous entrez l'extension de fichier, vous ne devez pas inclure le point.\)<br /><br /> Si vous fournissez une extension de fichier, l'Explorateur peut imprimer les documents de votre application sans lancer celle\-ci lorsque l'utilisateur place l'icône du document sur une icône d'imprimante.<br /><br /> Si vous ne spécifiez pas d'extension, l'utilisateur doit préciser une extension de fichier au moment de l'enregistrement des fichiers.  L'Assistant ne fournit pas d'extension de fichier par défaut.|  
|**ID du type de fichier**|Définit l'étiquette du type de document dans la base de registres.|  
  
 **Chaînes localisées**  
 Génère des chaînes associées à l'application et au document qui sont lues et employées par les utilisateurs de l'application, c'est pourquoi les chaînes sont traduites.  
  
|Option|Description|  
|------------|-----------------|  
|**Langue**|Indique la langue dans laquelle les chaînes sont affichées pour l'ensemble des zones situées sous **Chaînes traduites**.  Pour changer la valeur figurant dans cette zone, sélectionnez la langue appropriée sous **Langue des ressources** dans la page [Type d'application](../../mfc/reference/application-type-mfc-application-wizard.md) de l'Assistant Application MFC.|  
|**Titre du frame principal**|Définit le texte apparaissant en haut du frame principal de l'application.  Par défaut, il s'agit du nom du projet.|  
|**Nom de type de document**|Identifie le type de document sous lequel un document de l'application peut être regroupé.  Par défaut, il s'agit du nom du projet.  Le changement de la valeur par défaut n'entraîne la modification d'aucune autre option de la boîte de dialogue.|  
|**Nom de filtre**|Définit le nom que les utilisateurs peuvent indiquer pour rechercher des fichiers correspondant à votre type de fichier.  Cette option est disponible à partir des options **Type** et **Type** dans les boîtes de dialogue **Ouvrir** et **Enregistrer sous** Windows standard.  Par défaut, il s'agit du nom de projet accompagné du mot Files, suivis de l'extension indiquée dans **Extension de fichier**.  Par exemple, si votre projet se nomme Widget et que l'extension de fichier est .wgt, le **Nom de filtre** par défaut est Widget Files \(\*.wgt\).|  
|**Nom court de nouveau fichier**|Définit le nom apparaissant dans la boîte de dialogue `New` Windows standard, s'il existe plusieurs modèles de nouveau document.  Si votre application est un [serveur Automation](../../mfc/automation-servers.md), ce nom est utilisé en tant que nom court de votre objet Automation.  Par défaut, il s'agit du nom du projet.|  
|**Nom long du type de fichier**|Définit le nom de type de fichier dans la base de registres.  Si votre application est un serveur Automation, ce nom est utilisé en tant que nom long de votre objet Automation.  Par défaut, il s'agit du nom de projet accompagné du mot .Document.|  
  
## Voir aussi  
 [Assistant Application MFC](../../mfc/reference/mfc-application-wizard.md)