---
title: "Registry Entries | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Registre, application IDs"
  - "Registre, ATL services entries"
ms.assetid: 881989b7-61bb-459a-a13e-3bfcb33e184e
caps.latest.revision: 10
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Registry Entries
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

DCOM a introduit le concept des identificateurs d'application \(AppIDs\), les options de configuration group pour un ou plusieurs objets DCOM dans un emplacement centralisé dans le Registre.  Vous spécifiez un AppID en indiquant sa valeur dans l'AppID nommé valeur sous le CLSID de l'objet.  
  
 Par défaut, un service ATL généré utilise le CLSID comme un GUID pour son AppID.  Sous `HKEY_CLASSES_ROOT\AppID`, vous pouvez spécifier les entrées de DCOM\- détail.  Initialement, deux entrées existent :  
  
-   `LocalService`, avec une valeur égale au nom du service.  Si cette valeur existe, elle est utilisée au lieu de la clé d' `LocalServer32` sous le CLSID.  
  
-   `ServiceParameters`, avec une valeur égale à `–Service`.  Cette valeur spécifie les paramètres qui sont passés au service lorsqu'ils sont démarrés.  Notez que ces paramètres sont passés à la fonction d' `ServiceMain` du service, pas `WinMain`.  
  
 N'importe quel service DCOM doit également créer une autre clé sous `HKEY_CLASSES_ROOT\AppID`.  Cette clé est égale au nom de le fichier EXE et sert de référence croisée, car elle contient un pointeur de valeur AppID de revenir aux entrées de l'AppID.  
  
## Voir aussi  
 [Services](../atl/atl-services.md)