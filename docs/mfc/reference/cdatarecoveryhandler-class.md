---
title: "CDataRecoveryHandler Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CDataRecoveryHandler"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDataRecoveryHandler class"
ms.assetid: 7794802c-e583-4eba-90b9-2fed1a161f9c
caps.latest.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 19
---
# CDataRecoveryHandler Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CDataRecoveryHandler` sauvegarde des documents et les restaure automatiquement si une application s'arrête de façon inattendue.  
  
## Syntaxe  
  
```  
class CDataRecoveryHandler : public CObject  
```  
  
## Membres  
  
### Constructeurs  
  
|||  
|-|-|  
|[CDataRecoveryHandler::CDataRecoveryHandler](../Topic/CDataRecoveryHandler::CDataRecoveryHandler.md)|Construit un objet `CDataRecoveryHandler`.|  
  
### Méthodes  
  
|||  
|-|-|  
|[CDataRecoveryHandler::AutosaveAllDocumentInfo](../Topic/CDataRecoveryHandler::AutosaveAllDocumentInfo.md)|Enregistrez chaque fichier enregistré avec la classe d' `CDataRecoveryHandler` .|  
|[CDataRecoveryHandler::AutosaveDocumentInfo](../Topic/CDataRecoveryHandler::AutosaveDocumentInfo.md)|Enregistrez le document spécifié.|  
|[CDataRecoveryHandler::CreateDocumentInfo](../Topic/CDataRecoveryHandler::CreateDocumentInfo.md)|Ajoute un document à la liste de documents ouverts.|  
|[CDataRecoveryHandler::DeleteAllAutosavedFiles](../Topic/CDataRecoveryHandler::DeleteAllAutosavedFiles.md)|Supprime tous les fichiers sauvegardés automatiquement en cours.|  
|[CDataRecoveryHandler::DeleteAutosavedFile](../Topic/CDataRecoveryHandler::DeleteAutosavedFile.md)|Supprime le fichier enregistré automatiquement spécifié.|  
|[CDataRecoveryHandler::GenerateAutosaveFileName](../Topic/CDataRecoveryHandler::GenerateAutosaveFileName.md)|Génère le nom d'un fichier d'enregistrement automatique associé au nom de fichier fourni de document.|  
|[CDataRecoveryHandler::GetAutosaveInterval](../Topic/CDataRecoveryHandler::GetAutosaveInterval.md)|Retourne l'intervalle entre enregistrer des tests automatiquement.|  
|[CDataRecoveryHandler::GetAutosavePath](../Topic/CDataRecoveryHandler::GetAutosavePath.md)|Retourne le chemin d'accès des fichiers sauvegardés automatiquement.|  
|[CDataRecoveryHandler::GetDocumentListName](../Topic/CDataRecoveryHandler::GetDocumentListName.md)|Extrait le nom de document d'un objet d' `CDocument` .|  
|[CDataRecoveryHandler::GetNormalDocumentTitle](../Topic/CDataRecoveryHandler::GetNormalDocumentTitle.md)|Récupère le titre normal pour le document spécifié.|  
|[CDataRecoveryHandler::GetRecoveredDocumentTitle](../Topic/CDataRecoveryHandler::GetRecoveredDocumentTitle.md)|Crée et retourne le titre du document récupéré.|  
|[CDataRecoveryHandler::GetRestartIdentifier](../Topic/CDataRecoveryHandler::GetRestartIdentifier.md)|Récupère le seul identificateur de redémarrage de l'application.|  
|[CDataRecoveryHandler::GetSaveDocumentInfoOnIdle](../Topic/CDataRecoveryHandler::GetSaveDocumentInfoOnIdle.md)|Indique si `CDataRecoveryHandler` exécute un enregistrement automatique de la boucle inactive actuelle.|  
|[CDataRecoveryHandler::GetShutdownByRestartManager](../Topic/CDataRecoveryHandler::GetShutdownByRestartManager.md)|Indique si le gestionnaire de redémarrage a provoqué l'application de quitter.|  
|[CDataRecoveryHandler::Initialize](../Topic/CDataRecoveryHandler::Initialize.md)|Initialise `CDataRecoveryHandler`.|  
|[CDataRecoveryHandler::QueryRestoreAutosavedDocuments](../Topic/CDataRecoveryHandler::QueryRestoreAutosavedDocuments.md)|Affiche une boîte de dialogue à l'utilisateur pour chaque document que `CDataRecoveryHandler` a enregistré automatiquement.  La boîte de dialogue détermine si l'utilisateur souhaite restaurer le document enregistré automatiquement.|  
|[CDataRecoveryHandler::ReadOpenDocumentList](../Topic/CDataRecoveryHandler::ReadOpenDocumentList.md)|Charge la liste de document ouvert dans le Registre.|  
|[CDataRecoveryHandler::RemoveDocumentInfo](../Topic/CDataRecoveryHandler::RemoveDocumentInfo.md)|Supprime le document fourni dans la liste de document ouvert.|  
|[CDataRecoveryHandler::ReopenPreviousDocuments](../Topic/CDataRecoveryHandler::ReopenPreviousDocuments.md)|Ouvre précédemment les documents ouverts.|  
|[CDataRecoveryHandler::RestoreAutosavedDocuments](../Topic/CDataRecoveryHandler::RestoreAutosavedDocuments.md)|Restaure les documents sauvegardés automatiquement en fonction de l'entrée d'utilisateur.|  
|[CDataRecoveryHandler::SaveOpenDocumentList](../Topic/CDataRecoveryHandler::SaveOpenDocumentList.md)|Enregistre la liste actuelle de documents ouverts dans le Registre Windows.|  
|[CDataRecoveryHandler::SetAutosaveInterval](../Topic/CDataRecoveryHandler::SetAutosaveInterval.md)|Définit le temps entre enregistrer des cycles automatiquement en millisecondes.|  
|[CDataRecoveryHandler::SetAutosavePath](../Topic/CDataRecoveryHandler::SetAutosavePath.md)|Définit le répertoire dans lequel les fichiers sauvegardés automatiquement enregistrées.|  
|[CDataRecoveryHandler::SetRestartIdentifier](../Topic/CDataRecoveryHandler::SetRestartIdentifier.md)|Définit le seul identificateur de redémarrage pour cette instance d' `CDataRecoveryHandler`.|  
|[CDataRecoveryHandler::SetSaveDocumentInfoOnIdle](../Topic/CDataRecoveryHandler::SetSaveDocumentInfoOnIdle.md)|Définit si `CDataRecoveryHandler` enregistre les informations de document ouvert au Registre Windows pendant le cycle inactif actuel.|  
|[CDataRecoveryHandler::SetShutdownByRestartManager](../Topic/CDataRecoveryHandler::SetShutdownByRestartManager.md)|Définit si la sortie précédente de l'application a été provoquée par le gestionnaire de redémarrage.|  
|[CDataRecoveryHandler::UpdateDocumentInfo](../Topic/CDataRecoveryHandler::UpdateDocumentInfo.md)|Met à jour les informations pour un document étant donné que l'utilisateur a enregistré.|  
  
### Membres de données  
  
|||  
|-|-|  
|m\_bRestoringPreviousOpenDocs|Indique si le gestionnaire de récupération de données rouvre précédemment les documents ouverts.|  
|m\_bSaveDocumentInfoOnIdle|Indique si le gestionnaire de récupération de données sauvegarde des documents automatiquement sur la ligne boucle inactive.|  
|m\_bShutdownByRestartManager|Indique si le gestionnaire de redémarrage provoque l'application de quitter.|  
|m\_dwRestartManagerSupportFlags|Balises qui indiquent quel en charge le gestionnaire de redémarrage fournit pour l'application.|  
|m\_lstAutosavesToDelete|Une liste de fichiers sauvegardés automatiquement qui n'ont pas été supprimés lorsque les documents originaux ont été fermés.  Lorsque l'application s'arrête, le gestionnaire de redémarrage redémarre effacer les fichiers.|  
|m\_mapDocNameToAutosaveName|Une carte des noms de document aux noms de fichiers sauvegardés automatiquement.|  
|m\_mapDocNameToDocumentPtr|Une carte des noms de document aux pointeurs de [CDocument](../../mfc/reference/cdocument-class.md) .|  
|m\_mapDocNameToRestoreBool|Une carte des noms de document à un paramètre de type boolean qui indique s'il faut restaurer le document enregistré automatiquement.|  
|m\_mapDocumentPtrToDocName|Une carte des pointeurs d' `CDocument` aux noms de document.|  
|m\_mapDocumentPtrToDocTitle|Une carte des pointeurs d' `CDocument` dans les titres de document.  Ces titres sont utilisés pour enregistrer des fichiers.|  
|m\_nAutosaveInterval|Le temps en millisecondes entre sauvegarde automatiquement.|  
|m\_nTimerID|L'identificateur de la minuterie d'enregistrement automatique.|  
|m\_strAutosavePath|L'emplacement où les documents sauvegardés automatiquement enregistrées.|  
|m\_strRestartIdentifier|La représentation sous forme de chaîne GUID pour le gestionnaire de redémarrage.|  
  
## Notes  
 Le gestionnaire de redémarrage utilise la classe d' `CDataRecoveryHandler` pour contenir tous les documents ouverts et les enregistrer automatiquement si nécessaire.  Pour activer enregistrer automatiquement, utilisez la méthode de [CDataRecoveryHandler::SetSaveDocumentInfoOnIdle](../Topic/CDataRecoveryHandler::SetSaveDocumentInfoOnIdle.md) .  Cette méthode dirige `CDataRecoveryHandler` pour exécuter un enregistrement automatique sur la ligne boucle inactive.  Le gestionnaire de redémarrage appelle `SetSaveDocumentInfoOnIdle` lorsque `CDataRecoveryHandler` doit exécuter un enregistrement automatique.  
  
 Toutes les méthodes de classe d' `CDataRecoveryHandler` sont virtuelles.  Substituez les méthodes de cette classe pour créer votre propre gestionnaire personnalisé de récupération de données.  À moins que vous avez créé votre propre gestionnaire ou gestionnaire de redémarrage de récupération de données, n'instanciez pas un CDataRecoveryHandler.  [CWinApp Class](../../mfc/reference/cwinapp-class.md) crée un objet d' `CDataRecoveryHandler` à mesure qu'il est obligatoire.  
  
 Avant de pouvoir utiliser un objet d' `CDataRecoveryHandler` , vous devez appeler [CDataRecoveryHandler::Initialize](../Topic/CDataRecoveryHandler::Initialize.md).  
  
 Étant donné que la classe d' `CDataRecoveryHandler` est étroitement connectée au gestionnaire de redémarrage, `CDataRecoveryHandler` dépend du paramètre global `m_dwRestartManagerSupportFlags`.  Ce paramètre détermine les autorisations le gestionnaire de redémarrage un et comment il interagit avec votre application.  Pour incorporer le gestionnaire de redémarrage à une application existante, vous devez assigner à `m_dwRestartManagerSupportFlags` la valeur appropriée dans le constructeur de votre application principale.  Pour plus d'informations sur la façon d'utiliser le gestionnaire de redémarrage, consultez [Comment : ajouter la prise en charge du Gestionnaire de redémarrage](../../mfc/how-to-add-restart-manager-support.md).  
  
## Configuration requise  
 **en\-tête :** afxdatarecovery.h  
  
## Voir aussi  
 [Classes](../../mfc/reference/mfc-classes.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [CObject Class](../../mfc/reference/cobject-class.md)   
 [Comment : ajouter la prise en charge du Gestionnaire de redémarrage](../../mfc/how-to-add-restart-manager-support.md)