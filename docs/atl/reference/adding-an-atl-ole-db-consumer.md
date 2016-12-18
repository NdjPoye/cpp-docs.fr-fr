---
title: "Ajout d&#39;un consommateur OLE DB ATL | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "consommateurs OLE DB ATL"
  - "projets ATL, ajouter des consommateurs OLE DB ATL"
  - "OLE DB, ajouter un consommateur OLE DB ATL aux projets"
ms.assetid: f940a513-4e42-4148-b521-dd0d7dc89fa2
caps.latest.revision: 11
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Ajout d&#39;un consommateur OLE DB ATL
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Utilisez l'Assistant Consommateur OLE DB ATL pour ajouter un consommateur OLE DB ATL à un projet.  Un consommateur OLE DB ATL se compose d'une classe d'accesseur OLE DB et de liaisons de données nécessaires pour accéder à une source de données.  Le projet doit avoir été créé en tant qu'application ATL COM, MFC ou encore en tant qu'application MFC ou Win32 intégrant la prise en charge ATL \(que l'Assistant Consommateur OLE DB ATL ajoute automatiquement\).  
  
 **Note** vous pouvez ajouter un consommateur OLE DB à un projet MFC.  En ce cas, l'Assistant Consommateur OLE DB ATL ajoute la prise en charge COM nécessaire à votre projet.  Cela suppose que lorsque vous avez créé le projet MFC, vous avez activé la case à cocher **Contrôles ActiveX** \(dans la page **Fonctionnalités avancées** de l'Assistant Application de projets MFC\), qui est activée par défaut.  Lorsque cette option est sélectionnée, l'application appelle **CoInitialize** et **CoUninitialize**.  Si vous n'avez pas activé la case à cocher **Contrôles ActiveX** lors de la création du projet MFC, vous devez appeler **CoInitialize** et **CoUninitialize** dans votre code principal.  
  
### Pour ajouter un consommateur OLE DB ATL à votre projet  
  
1.  Dans l'Affichage de classes, cliquez avec le bouton droit sur le projet.  Dans le menu contextuel, cliquez sur **Ajouter**, puis sur **Ajouter une classe**.  
  
2.  Dans le dossier Visual C\+\+, double\-cliquez sur l'icône **Consommateur OLE DB ATL** ou sélectionnez\-la, puis cliquez sur **Ouvrir**.  
  
     L'Assistant Consommateur OLE DB ATL s'ouvre.  
  
3.  Définissez les paramètres comme indiqué dans [Assistant Consommateur OLE DB ATL](../../atl/reference/atl-ole-db-consumer-wizard.md).  
  
4.  Cliquez sur **Terminer** pour fermer l'Assistant.  Le code de consommateur OLE DB que vous venez de créer est inséré dans le projet.  
  
## Voir aussi  
 [Ajout de fonctionnalités à l'aide des Assistants Code](../../ide/adding-functionality-with-code-wizards-cpp.md)