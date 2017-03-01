---
title: MFC Macros and Globals | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.mfc.macros
dev_langs:
- C++
helpviewer_keywords:
- MFC, global functions and variables
- MFC, macros
- global functions, MFC
- macros, MFC
- global functions
- global variables, MFC
- Afx naming convention
- macros
ms.assetid: add4e33f-0e62-4d27-be14-896cb8675d22
caps.latest.revision: 18
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: d26b374e233326ac5acc97486edc8d38e6bf5d81
ms.openlocfilehash: 75db28c7be1ab497ba9656136d22b114b488c4ae
ms.lasthandoff: 02/24/2017

---
# <a name="mfc-macros-and-globals"></a>Macros et objet Globals MFC
La bibliothèque Microsoft Foundation Class peut être divisée en deux sections principales : (1) les classes MFC et les macros (2) et les globals. Si une fonction ou une variable n’est pas un membre d’une classe, il est une fonction globale ou une variable.  
  
 La bibliothèque MFC et la bibliothèque ATL (Active Template Library) partagent les macros de conversion de chaînes. Pour plus d’informations, consultez [Macros de Conversion de chaînes](../../atl/reference/string-conversion-macros.md) dans la documentation de ATL.  
  
 Les macros MFC et des variables globales offrent des fonctionnalités dans les catégories suivantes.  
  
## <a name="general-mfc"></a>MFC générales  
  
-   [Types de données](../../mfc/reference/data-types-mfc.md)  
  
-   [Conversion de type des objets de classe MFC](../../mfc/reference/type-casting-of-mfc-class-objects.md)  
  
-   [Services du modèle objet d’exécution](../../mfc/reference/run-time-object-model-services.md)  
  
-   [Services de diagnostic](../../mfc/reference/diagnostic-services.md)  
  
-   [Traitement des exceptions](../../mfc/reference/exception-processing.md)  
  
-   [Mise en forme de CString et affichage de la boîte de message](../../mfc/reference/cstring-formatting-and-message-box-display.md)  
  
-   [Tables des messages](../../mfc/reference/message-map-macros-mfc.md)  
  
-   [Gestion des informations et des applications](../../mfc/reference/application-information-and-management.md)  
  
-   [ID de commande et de fenêtre standard](../../mfc/reference/standard-command-and-window-ids.md)  
  
-   [Assistants de classe de collection](../../mfc/reference/collection-class-helpers.md)  
  
-   [Fonctions d’image bitmap tramée et grise](../../mfc/reference/gray-and-dithered-bitmap-functions.md)  
  
-   [Routines d’échange (DDX) de données de boîte de dialogue standard](../../mfc/reference/standard-dialog-data-exchange-routines.md)  
  
-   [Routines de validation (DDV) de données de boîte de dialogue standard](../../mfc/reference/standard-dialog-data-validation-routines.md)  
  
-   [AFX, Messages](../../mfc/reference/afx-messages.md)  
  
-   [Styles de contrôle de barre d’outils](../../mfc/reference/toolbar-control-styles.md)  
  
-   [CMFCImagePaintArea::IMAGE_EDIT_MODE (énumération)](cmfcimagepaintarea-image-edit-mode-enumeration.md)  

  
## <a name="database"></a>Base de données  
  
-   [Enregistrer les fonctions Field Exchange (RFX)](../../mfc/reference/record-field-exchange-functions.md) et [les fonctions RFX en bloc (bulk RFX)](../../mfc/reference/record-field-exchange-functions.md) pour les classes ODBC MFC  
  
-   [Enregistrer les fonctions field exchange (DFX)](../../mfc/reference/record-field-exchange-functions.md) pour les classes DAO MFC  
  
-   [Fonctions d’échange de données de boîtes de dialogue (DDX) pour CRecordView et CDaoRecordView](../../mfc/reference/dialog-data-exchange-functions-for-crecordview-and-cdaorecordview.md) (classes DAO et ODBC MFC)  
  
-   [Échange de données de la boîte de dialogue de fonctions (DDX) pour les contrôles OLE](../../mfc/reference/dialog-data-exchange-functions-for-ole-controls.md)  
  
-   [Macros et objet globals pour vous aider à appeler directement les fonctions de Open Database Connectivity (ODBC) API](../../mfc/reference/database-macros-and-globals.md)  
  
-   [Arrêt et initialisation du moteur de base de données DAO](../../mfc/reference/dao-database-engine-initialization-and-termination.md)  
  
## <a name="internet"></a>Internet  
  
-   [Objet globals d’analyse des URL Internet](../../mfc/reference/internet-url-parsing-globals.md)  
  
## <a name="dhtml--dhtml-event-maps"></a>DHTML / mappe événement DHTML  
  
-   [Les macros d’assistance (DDX) d’échange de données de boîte de dialogue DHTML](../../mfc/reference/ddx-dhtml-helper-macros.md)  
  
-   [Tables d’événements DHTML](../../mfc/reference/dhtml-event-maps.md)  
  
## <a name="ole"></a>OLE  
  
-   [Initialisation d’OLE](../../mfc/reference/ole-initialization.md)  
  
-   [Contrôle d’application](../../mfc/reference/application-control.md)  
  
-   [Tables de dispatch](../../mfc/reference/dispatch-maps.md)  
  
 En outre, MFC fournit une fonction appelée [AfxEnableControlContainer](http://msdn.microsoft.com/library/7aa0b9d2-5329-4bc3-9d41-856e30fe2c2b) que permet de n’importe quel conteneur OLE développée avec MFC 4.0 prennent en charge incorporée de contrôles OLE.  
  
## <a name="ole-controls"></a>Contrôles OLE  
  
-   [Constantes de type paramètre Variant](../../mfc/reference/variant-parameter-type-constants.md)  
  
-   [Accès à la bibliothèque type](../../mfc/reference/type-library-access.md)  
  
-   [Pages de propriétés](../../mfc/reference/property-pages-mfc.md)  
  
-   [Tables d’événements](../../mfc/reference/event-maps.md)  
  
-   [Tables de récepteurs d’événements](../../mfc/reference/event-sink-maps.md)  
  
-   [Mappages de connexion](../../mfc/reference/connection-maps.md)  
  
-   [Inscrire des contrôles OLE](../../mfc/reference/registering-ole-controls.md)  
  
-   [Les fabriques de classes et les licences](../../mfc/reference/class-factories-and-licensing.md)  
  
-   [Persistance des contrôles OLE](../../mfc/reference/persistence-of-ole-controls.md)  
  
 La première partie de cette section décrit chacune des catégories précédentes brièvement et répertorie les variables globales et les macros dans la catégorie, ainsi que de brèves descriptions de fonctionnalités. Ce sont des descriptions des fonctions globales, des variables globales et les macros dans la bibliothèque MFC.  
  
> [!NOTE]
>  De nombreuses fonctions globales commencent par le préfixe « Afx », mais certains, par exemple, les fonctions d’échange de données boîte de dialogue et de nombreuses fonctions de la base de données, ne suivent pas cette convention. Toutes les variables globales commencent par « afx » comme préfixe. Les macros ne commencent pas par n’importe quel préfixe particulier, mais ils sont écrits en majuscules.  
  
## <a name="see-also"></a>Voir aussi  
 [Vue d’ensemble de la classe](../../mfc/class-library-overview.md)




