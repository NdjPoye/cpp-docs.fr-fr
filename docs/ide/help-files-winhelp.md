---
title: Fichiers d’aide (WinHelp) | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- file types [C++], WinHelp files
ms.assetid: 4fdcbd66-66b0-4866-894a-fd7b4c2557e4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 505506c7f3a14a73c6b0c859a70938fee3eed69e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="help-files-winhelp"></a>Fichiers d'aide (WinHelp)
Les fichiers suivants sont créés lorsque vous ajoutez le type WinHelp de prise en charge de l’aide à votre application en sélectionnant le **contextuelle** case à cocher, puis en sélectionnant **format WinHelp** dans les [Fonctionnalités avancées](../mfc/reference/advanced-features-mfc-application-wizard.md) page de l’Assistant Application MFC.  
  
|Nom de fichier|Emplacement du répertoire|Emplacement dans l'Explorateur de solutions|Description|  
|---------------|------------------------|--------------------------------|-----------------|  
|*Nomproj*.hpj|*Nomproj*\hlp|Fichiers sources|Le fichier de projet d’aide utilisé par le compilateur d’aide pour créer votre programme ou le fichier d’aide du contrôle.|  
|*Nomproj*.rtf|*Nomproj*\hlp|Fichiers d’aide|Contient des rubriques de modèle que vous pouvez modifier et les informations sur la personnalisation de votre fichier .hpj.|  
|*Nomproj*.cnt|*Nomproj*\hlp|Fichiers d’aide|Fournit la structure pour le **contenu** fenêtre dans l’aide de Windows.|  
|Makehelp.bat|*Nomproj*|Fichiers sources|Utilisé par le système pour générer le projet d’aide lors de la compilation du projet.|  
|Print.RTF|*Nomproj*\hlp|Fichiers d’aide|Créé si votre projet inclut la prise en charge l’impression (la valeur par défaut). Décrit les commandes d’impression et les boîtes de dialogue.|  
|*.bmp|*Nomproj*\hlp|Fichiers de ressources|Contenir des images pour les rubriques d’aide générées différents.|  
  
 Vous pouvez ajouter la prise en charge de WinHelp à un projet de contrôle ActiveX MFC en sélectionnant **générer les fichiers d’aide** dans les [paramètres de l’Application](../mfc/reference/application-settings-mfc-activex-control-wizard.md) onglet de l’Assistant contrôle ActiveX MFC. Les fichiers suivants sont ajoutés à votre projet lorsque vous ajoutez la prise en charge de l’aide pour un contrôle ActiveX MFC :  
  
|Nom de fichier|Emplacement du répertoire|Emplacement dans l'Explorateur de solutions|Description|  
|---------------|------------------------|--------------------------------|-----------------|  
|*Nomproj*.hpj|*Nomproj*\hlp|Fichiers sources|Le fichier de projet utilisé par le compilateur d’aide pour créer votre programme ou le fichier d’aide du contrôle.|  
|*Nomproj*.rtf|*Nomproj*\hlp|Projet|Contient des rubriques de modèle que vous pouvez modifier et les informations sur la personnalisation de votre fichier .hpj.|  
|Makehelp.bat|*Nomproj*|Fichiers sources|Utilisé par le système pour générer le projet d’aide lors de la compilation du projet.|  
|Bullet.bmp|*Nomproj*|Fichiers de ressources|Utilisé par le fichier des rubriques aide standard pour représenter les listes à puces.|  
  
## <a name="see-also"></a>Voir aussi  
 [Types de fichiers créés pour les projets Visual C++](../ide/file-types-created-for-visual-cpp-projects.md)