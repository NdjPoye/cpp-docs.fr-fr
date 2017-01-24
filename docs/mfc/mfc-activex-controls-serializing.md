---
title: "Contr&#244;les ActiveX MFC&#160;: s&#233;rialisation | Microsoft Docs"
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
  - "_wVerMinor"
  - "DoPropExchange"
  - "_wVerMajor"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DoPropExchange (méthode)"
  - "ExchangeVersion (méthode)"
  - "GetVersion (méthode)"
  - "contrôles ActiveX MFC, sérialisation"
  - "contrôles ActiveX MFC, prise en charge des versions"
  - "contrôle de version des contrôles ActiveX"
  - "wVerMajor global (constante)"
  - "wVerMinor global (constante)"
ms.assetid: 9d57c290-dd8c-4853-b552-6f17f15ebedd
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Contr&#244;les ActiveX MFC&#160;: s&#233;rialisation
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Cet article explique comment sérialiser un contrôle ActiveX.  La sérialisation est le processus de lire ou d'écrire dans un support de stockage permanent, tel qu'un fichier de disque.  La bibliothèque Microsoft Foundation Class \(MFC\) fournit une prise en charge intégrée pour la sérialisation de la classe `CObject`.  `COleControl` étend cette prise en charge des contrôles ActiveX via l'utilisation d'un mécanisme d'échange de propriétés.  
  
 La sérialisation des contrôles ActiveX est implémentée en remplaçant [COleControl::DoPropExchange](../Topic/COleControl::DoPropExchange.md).  Cette fonction, appelée pendant le chargement et l'enregistrement de l'objet de contrôle, stocke toutes les propriétés qui sont exécutées avec une variable membre ou une variable membre à la notification de modification.  
  
 Les rubriques suivantes expliquent les principaux problèmes liés à sérialiser un contrôle ActiveX :  
  
-   Implémentation de la fonction de `DoPropExchange` pour sérialiser l'objet de contrôle  
  
-   [Personnalisation du processus de sérialisation](#_core_customizing_the_default_behavior_of_dopropexchange)  
  
-   [Implémenter la prise en charge des versions](#_core_implementing_version_support)  
  
##  <a name="_core_implementing_the_dopropexchange_function"></a> Implémentation de la fonction de FaireEchangeProprietaire  
 Lorsque vous utilisez l'Assistant Contrôle ActiveX pour générer le projet de contrôle, plusieurs fonctions gestionnaires par défaut sont ajoutées automatiquement à la classe de contrôle, y compris l'implémentation par défaut de [COleControl::DoPropExchange](../Topic/COleControl::DoPropExchange.md).  L'exemple suivant montre le code ajouté aux classes générées à l'aide de l'Assistant Contrôle ActiveX :  
  
 [!code-cpp[NVC_MFC_AxUI#43](../mfc/codesnippet/CPP/mfc-activex-controls-serializing_1.cpp)]  
  
 Si vous souhaitez rendre une propriété persistante, modifiez `DoPropExchange` en ajoutant un appel à la fonction d'échange de propriétés.  L'exemple suivant illustre la sérialisation d'une propriété booléenne personnalisée de CircleShape, où la propriété de CircleShape a une valeur par défaut de **TRUE**:  
  
 [!code-cpp[NVC_MFC_AxSer#1](../mfc/codesnippet/CPP/mfc-activex-controls-serializing_2.cpp)]  
[!code-cpp[NVC_MFC_AxSer#2](../mfc/codesnippet/CPP/mfc-activex-controls-serializing_3.cpp)]  
  
 Le tableau suivant répertorie les fonctions possibles d'échange des propriétés que vous pouvez utiliser pour sérialiser les propriétés du contrôle :  
  
|Fonctions d'échange de propriétés|Objectif|  
|---------------------------------------|--------------|  
|**PX\_Blob\( \)**|Sérialise un type d'objet binaire large \(BLOB\) propriété d'information.|  
|**PX\_Bool\( \)**|Sérialise une propriété de type booléen.|  
|**PX\_Color\( \)**|Sérialise une propriété de couleur de type.|  
|**PX\_Currency\( \)**|Sérialise une propriété de type **CY**.|  
|**PX\_Double\( \)**|Sérialise une propriété de type **double**.|  
|**PX\_Font\( \)**|Sérialise une propriété de type de police de caractères.|  
|**PX\_Float\( \)**|Sérialise une propriété de type de **float**.|  
|**PX\_IUnknown\( \)**|Sérialise une propriété de type `LPUNKNOWN`.|  
|**PX\_Long\( \)**|Sérialise une propriété de type **long**.|  
|**PX\_Picture\( \)**|Sérialise une propriété de type image.|  
|**PX\_Short\( \)**|Sérialise une propriété de type **short**.|  
|**PX\_String\( \)**|Sérialise une propriété de type `CString`.|  
|**PX\_ULong\( \)**|Sérialise une propriété de type **long**.|  
|**PX\_UShort\( \)**|Sérialise une propriété de type **USHORT**.|  
  
 Pour plus d'informations sur ces fonctions d'échange de propriétés, consultez le [Persistance des contrôles OLE](../mfc/reference/persistence-of-ole-controls.md) dans *le guide de MFC*.  
  
##  <a name="_core_customizing_the_default_behavior_of_dopropexchange"></a> Personnaliser le comportement par défaut de DoPropExchange  
 L'implémentation par défaut de **DoPropertyExchange** \(comme illustré rubrique précédente\) effectue un appel à la classe de base `COleControl`.  Cela sérialise le jeu de propriétés automatiquement prises en charge par `COleControl`, qui utilise davantage d'espace de stockage qu'à sérialiser uniquement les propriétés personnalisées du contrôle.  Supprimer cet appel permet à votre objet de sérialiser uniquement les propriétés que vous considérez importantes.  Propriété stock en états que le contrôle est implémenté n'est pas sérialisée en enregistrant ou lors de le chargement de l'objet de contrôle à moins que vous n'ajoutiez explicitement les appels de **PX\_** pour eux.  
  
##  <a name="_core_implementing_version_support"></a> Implémenter la prise en charge des versions  
 La prise en charge des versions permet à un contrôle ActiveX modifié pour ajouter de nouvelles propriétés persistantes, et peut toujours détecter et charger l'état permanent créé par une version précédente du contrôle.  Pour rendre la version d'un contrôle disponible dans le cadre de ses données persistantes, appelez [COleControl::ExchangeVersion](../Topic/COleControl::ExchangeVersion.md) dans la fonction `DoPropExchange` du contrôle.  Cet appel est automatiquement inséré si le contrôle ActiveX a été créé à l'aide de l'Assistant Contrôle ActiveX.  Il peut être supprimé si la prise en charge des versions n'est pas nécessaire.  Toutefois, le coût de la taille de contrôle est très faible \(4 octets\) pour la flexibilité ajoutée à la prise en charge des versions fournit.  
  
 Si le contrôle n'a pas été créé à l'aide de l'Assistant Contrôle ActiveX, ajoutez un appel à `COleControl::ExchangeVersion` en insérant la ligne suivante au début de la fonction de `DoPropExchange` \(avant l'appel à `COleControl::DoPropExchange`\) :  
  
 [!code-cpp[NVC_MFC_AxSer#1](../mfc/codesnippet/CPP/mfc-activex-controls-serializing_2.cpp)]  
[!code-cpp[NVC_MFC_AxSer#3](../mfc/codesnippet/CPP/mfc-activex-controls-serializing_4.cpp)]  
  
 Utilisez tout `DWORD` comme numéro de version.  Projets générés par l'utilisation **\_wVerMinor** et **\_wVerMajor** de l'Assistant Contrôle ActiveX comme valeur par défaut.  Ce sont des constantes globales définies dans le fichier d'implémentation de classe de contrôle ActiveX du projet.  Dans le reste de la fonction de `DoPropExchange`, vous pouvez appeler [CPropExchange::GetVersion](../Topic/CPropExchange::GetVersion.md) à tout moment pour récupérer la version que vous enregistrez ou récupérer.  
  
 Dans l'exemple suivant, la version 1 de cette simple vérification une seule propriété « ReleaseDate ».  La version 2 ajoute une propriété « OriginalDate ».  Si le contrôle est chargé de charger l'état permanent de la version antérieure, il initialise la variable membre de la nouvelle propriété la valeur par défaut.  
  
 [!code-cpp[NVC_MFC_AxSer#4](../mfc/codesnippet/CPP/mfc-activex-controls-serializing_5.cpp)]  
[!code-cpp[NVC_MFC_AxSer#3](../mfc/codesnippet/CPP/mfc-activex-controls-serializing_4.cpp)]  
  
 Par défaut, un contrôle «convertit» les anciennes données correspondant au dernier format.  Par exemple, si la version 2 d'un contrôle charge les données enregistrées par la version 1, il écrit le format version 2 lorsqu'il est stocké à nouveau.  Si vous voulez un contrôle pour enregistrer des données dans la lecture de bout de format, passez **FALSE** en tant que troisième paramètre en appelant `ExchangeVersion`.  Ce troisième paramètre est facultatif et est **TRUE** par défaut.  
  
## Voir aussi  
 [Contrôles ActiveX MFC](../mfc/mfc-activex-controls.md)