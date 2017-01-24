---
title: "Macros et objet Globals MFC | Microsoft Docs"
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
  - "vc.mfc.macros"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Afx (convention de noms)"
  - "fonctions globales"
  - "fonctions globales, MFC"
  - "variables globales, MFC"
  - "macros"
  - "macros, MFC"
  - "MFC, fonctions et variables globales"
  - "MFC, macros"
ms.assetid: add4e33f-0e62-4d27-be14-896cb8675d22
caps.latest.revision: 18
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Macros et objet Globals MFC
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

La bibliothèque MFC \(Microsoft Foundation Class\) peut être divisée en deux sections principales : \(1\) les classes MFC et \(2\) les macros et les classes globales.  Si une fonction ou une variable n'est pas membre d'une classe, c'est une fonction ou une variable globale.  
  
 La bibliothèque MFC et l'ATL \(ATL\) partagent des macros de conversion de chaînes.  Pour plus d'informations, consultez [String Conversion Macros](../../atl/reference/string-conversion-macros.md) dans la documentation du Kit de développement logiciel \(ATL\).  
  
 Les macros MFC et les globales offrent des fonctionnalités dans les catégories suivantes.  
  
## Touches générales du fabricant d'ordinateurs MFC  
  
-   [Types de données](../../mfc/reference/data-types-mfc.md)  
  
-   [Cast de type des objets de classe MFC](../../mfc/reference/type-casting-of-mfc-class-objects.md)  
  
-   [Services du modèle objet au moment de l'exécution](../../mfc/reference/run-time-object-model-services.md)  
  
-   [Services de diagnostic](../../mfc/reference/diagnostic-services.md)  
  
-   [Traitement des exceptions](../../mfc/reference/exception-processing.md)  
  
-   [Mise en forme de CString et affichage des boîtes de message](../../mfc/reference/cstring-formatting-and-message-box-display.md)  
  
-   [Cartes des messages](../../mfc/reference/message-map-macros-mfc.md)  
  
-   [Informations et gestion de l'application](../../mfc/reference/application-information-and-management.md)  
  
-   [ID de fenêtre et commande standard](../../mfc/reference/standard-command-and-window-ids.md)  
  
-   [Programmes d'assistance pour les classes de collection](../../mfc/reference/collection-class-helpers.md)  
  
-   [Fonctions d'image bitmap tramée et grise](../../mfc/reference/gray-and-dithered-bitmap-functions.md)  
  
-   [Routines d'échange de données de boîte de dialogue standard \(DDX\)](../../mfc/reference/standard-dialog-data-exchange-routines.md)  
  
-   [Routines de validation des données de boîte de dialogue standard \(DDV\)](../../mfc/reference/standard-dialog-data-validation-routines.md)  
  
-   [AFX, messages](../../mfc/reference/afx-messages.md)  
  
-   [Styles de contrôle ToolBar](../../mfc/reference/toolbar-control-styles.md)  
  
-   [CMFCImagePaintArea::IMAGE\_EDIT\_MODE Enumeration](../../mfc/reference/cmfcimagepaintarea-image-edit-mode-enumeration.md)  
  
## Base de données  
  
-   [Fonctions de l'échange des champs \(RFX\)](../../mfc/reference/record-field-exchange-functions.md) et [Fonctions du mécanisme RFX en bloc \(Bulk RFX\)](../../mfc/reference/record-field-exchange-functions.md) pour les classes ODBC MFC  
  
-   [Fonctions de l'échange des champs \(DFX\)](../../mfc/reference/record-field-exchange-functions.md) pour les classes DAO MFC  
  
-   [L'échange de données de boîtes de dialogue \(DDX\) fonctionne pour CRecordView et CDaoRecordView](../../mfc/reference/dialog-data-exchange-functions-for-crecordview-and-cdaorecordview.md) \(classes DAO et ODBC MFC\)  
  
-   [Fonctions d'échange de données de boîtes de dialogue \(DDX\) pour contrôles OLE](../../mfc/reference/dialog-data-exchange-functions-for-ole-controls.md)  
  
-   [Macros et globales pour simplifier les fonctions API de l'ODBC directement](../../mfc/reference/database-macros-and-globals.md)  
  
-   [Initialisation et terminaison du moteur de base de données DAO](../../mfc/reference/dao-database-engine-initialization-and-termination.md)  
  
## Internet  
  
-   [Objet Globals d'analyse des URL Internet](../../mfc/reference/internet-url-parsing-globals.md)  
  
## DHTML\/ Cartes d'événements DHTML  
  
-   [Macros d'assistance d'échange de données de boîtes de dialogue \(DDX\) DHTML](../../mfc/reference/ddx-dhtml-helper-macros.md)  
  
-   [DHTML, cartes d'événements](../../mfc/reference/dhtml-event-maps.md)  
  
## OLE  
  
-   [initialisation d'OLE](../../mfc/reference/ole-initialization.md)  
  
-   [Contrôle d'application](../../mfc/reference/application-control.md)  
  
-   [Cartes de dispatch](../../mfc/reference/dispatch-maps.md)  
  
 En outre, MFC fournit une fonction appelée [AfxEnableControlContainer](../Topic/AfxEnableControlContainer.md) qui permet à tout conteneur OLE développé avec MFC 4,0 de prendre entièrement en charge les contrôles OLE incorporés.  
  
## Contrôles OLE  
  
-   [Constantes de type paramètre variant](../../mfc/reference/variant-parameter-type-constants.md)  
  
-   [Accès à la bibliothèque de types](../../mfc/reference/type-library-access.md)  
  
-   [Pages de propriétés](../../mfc/reference/property-pages-mfc.md)  
  
-   [Cartes d'événements](../../mfc/reference/event-maps.md)  
  
-   [Cartes de récepteurs d'événements](../../mfc/reference/event-sink-maps.md)  
  
-   [Cartes de connexions](../../mfc/reference/connection-maps.md)  
  
-   [Inscription des contrôles OLE](../../mfc/reference/registering-ole-controls.md)  
  
-   [Fabriques des classes et gestion des licences](../../mfc/reference/class-factories-and-licensing.md)  
  
-   [Persistance des contrôles OLE](../../mfc/reference/persistence-of-ole-controls.md)  
  
 La première partie de cette section décrit brièvement chacune des catégories précédentes et répertorie les globales et les macros dans la catégorie, offre de brèves descriptions de fonctionnalité.  Après cela sont les descriptions des fonctions, des variables globales, et des macros dans la bibliothèque MFC.  
  
> [!NOTE]
>  De nombreuses fonction globales commence avec le préfixe « Afx », mais certaines, par exemple, des fonctions d'échange de données de boîtes de dialogue \(DDX\) et de nombreuses fonctions de base de données, ne suivent pas cette convention.  Toutes les variables globales par « afx » comme préfixe.  Les macros ne commencent pas par un préfixe spécifique, mais elles sont écrites en majuscules.  
  
## Voir aussi  
 [Vue d'ensemble des classes](../../mfc/class-library-overview.md)