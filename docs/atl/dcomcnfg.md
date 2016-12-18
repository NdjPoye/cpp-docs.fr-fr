---
title: "DCOMCNFG | Microsoft Docs"
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
  - "DCOMCNFG"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DCOM, configuring in ATL"
  - "DCOMCNFG utility"
ms.assetid: 5a8126e9-ef27-40fb-a66e-9dce8d1a7e80
caps.latest.revision: 10
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# DCOMCNFG
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**DCOMCNFG** est un utilitaire Windows NT 4,0 qui vous permet de configurer différentes configurations de DCOM\- détail dans le Registre.  La fenêtre de **DCOMCNFG** a trois pages : Sécurité par défaut, les propriétés par défaut, et applications.  Sous Windows 2000 une quatrième page, protocoles par défaut, est présente.  
  
## Page par défaut de sécurité  
 Vous pouvez utiliser la page par défaut de sécurité pour spécifier les autorisations par défaut pour les objets sur le système.  La page par défaut de sécurité a trois sections : Access, lancement, et configuration.  Pour modifier les valeurs par défaut d'une section, cliquez sur le bouton correspondant de **Modifier** .  Ces paramètres de sécurité par défaut sont stockés dans le Registre sous `HKEY_LOCAL_MACHINE\Software\Microsoft\OLE`.  
  
## Page par défaut de protocoles  
 Cette page répertorie l'ensemble des protocoles réseau disponibles à DCOM sur cet ordinateur.  La commande indique la priorité dans lequel ils seront utilisés ; le premier dans la liste a la priorité la plus élevée.  Les fournisseurs peuvent être ajoutés ou supprimés de cette page.  
  
## Page de propriétés par défaut  
 Dans la page de propriétés par défaut, vous devez activer la case à cocher de **Activer Distributed COM \(DCOM\) sur cet ordinateur** si vous souhaitez que les clients sur d'autres ordinateurs pour accéder aux objets COM qui s'exécutent sur cet ordinateur.  La sélection de cette option affecte la valeur d' `HKEY_LOCAL_MACHINE\Software\Microsoft\OLE\EnableDCOM` à `Y`.  
  
## Page d'application  
 Vous modifiez les paramètres pour un objet particulier avec la page d'application.  Sélectionnez simplement l'application de la liste et cliquez sur le bouton **Propriétés** .  La fenêtre Propriétés contient cinq pages :  
  
-   La page en confirmant l'application que vous utilisez.  
  
-   La page d'emplacement vous permet de spécifier où l'application doit s'exécuter lorsqu'un client appelle `CoCreateInstance` sur le CLSID approprié.  Si vous activez la case à cocher de **Exécuter l’application sur l’ordinateur suivant** et entrez un nom d'ordinateur, une valeur d' `RemoteServerName` est ajoutée sous l'AppID pour cette application.  Désactiver la case à cocher de **Run application on this computer** renomme la valeur d' `LocalService` à `_LocalService` et la désactivation, de ce fait.  
  
-   La page sécurité est semblable à la page par défaut de sécurité recherchée dans la fenêtre de **DCOMCNFG** , sauf que ces paramètres s'appliquent uniquement à l'application actuelle.  Là encore, les paramètres sont stockés sous l'AppID pour cet objet.  
  
-   La page d'identification identifie l'utilisateur est utilisé pour exécuter l'application.  
  
-   La page de points de terminaison répertorie l'ensemble des protocoles et de points de terminaison disponibles pour une utilisation par les clients du serveur sélectionné DCOM.  
  
## Voir aussi  
 [Services](../atl/atl-services.md)