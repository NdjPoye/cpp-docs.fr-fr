---
title: "Fichiers d&#39;aide (WinHelp) | Microsoft Docs"
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
  - "types de fichiers (C++), fichiers WinHelp"
ms.assetid: 4fdcbd66-66b0-4866-894a-fd7b4c2557e4
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Fichiers d&#39;aide (WinHelp)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les fichiers suivants sont créés lorsque vous ajoutez à votre application une prise en charge de l'aide de type WinHelp, ceci en activant la case à cocher **Aide contextuelle** puis en sélectionnant **Format WinHelp** dans la page [Fonctionnalités avancées](../mfc/reference/advanced-features-mfc-application-wizard.md) de l'Assistant Application MFC.  
  
|Nom du fichier|Emplacement dans les répertoires|Emplacement dans l'Explorateur de solutions|Description|  
|--------------------|--------------------------------------|-------------------------------------------------|-----------------|  
|*Nomprojet*.hpj|*Nomprojet*\\hlp|Fichiers sources|Fichier projet d'aide dont se sert le compilateur d'aide pour créer le fichier d'aide de votre programme ou contrôle.|  
|*Nomprojet*.rtf|*Nomprojet*\\hlp|Fichiers d'aide|Contient des rubriques modèles que vous pouvez modifier, et des informations sur la personnalisation de votre fichier .hpj.|  
|*Nomprojet*.cnt|*Nomprojet*\\hlp|Fichiers d'aide|Fournit la structure de la fenêtre **Sommaire** dans l'aide Windows.|  
|Makehelp.bat|*Nomprojet*|Fichiers sources|Fichier utilisé par le système pour générer le projet d'aide lors de la compilation du projet.|  
|Print.rtf|*Nomprojet*\\hlp|Fichiers d'aide|Fichier créé si votre projet offre une prise en charge de l'impression \(option par défaut\).  Ce fichier décrit les commandes et boîtes de dialogue relatives à l'impression.|  
|\*.bmp|*Nomprojet*\\hlp|Fichiers de ressources|Contient les images affichées dans les différentes rubriques d'aide générées.|  
  
 Vous pouvez ajouter une prise en charge de WinHelp à un projet de contrôle ActiveX MFC, ceci en sélectionnant **Générer les fichiers d'aide** sous l'onglet [Paramètres de l'application](../mfc/reference/application-settings-mfc-activex-control-wizard.md) de l'Assistant Contrôle ActiveX MFC.  Les fichiers suivants sont ajoutés à votre projet lorsque vous ajoutez la prise en charge de l'aide à un contrôle ActiveX MFC :  
  
|Nom du fichier|Emplacement dans les répertoires|Emplacement dans l'Explorateur de solutions|Description|  
|--------------------|--------------------------------------|-------------------------------------------------|-----------------|  
|*Nomprojet*.hpj|*Nomprojet*\\hlp|Fichiers sources|Fichier projet dont se sert le compilateur d'aide pour créer le fichier d'aide de votre programme ou contrôle.|  
|*Nomprojet*.rtf|*Nomprojet*\\hlp|Projet|Contient des rubriques modèles que vous pouvez modifier, et des informations sur la personnalisation de votre fichier .hpj.|  
|Makehelp.bat|*Nomprojet*|Fichiers sources|Fichier utilisé par le système pour générer le projet d'aide lors de la compilation du projet.|  
|Bullet.bmp|*Nomprojet*|Fichiers de ressources|Fichier utilisé pour représenter les listes à puces dans les rubriques d'aide standard.|  
  
## Voir aussi  
 [Types de fichiers créés pour les projets Visual C\+\+](../ide/file-types-created-for-visual-cpp-projects.md)