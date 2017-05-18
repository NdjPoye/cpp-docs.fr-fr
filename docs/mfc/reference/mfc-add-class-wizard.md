---
title: MFC Assistant Ajouter une classe | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.codewiz.class.mfc.simple.overview
dev_langs:
- C++
helpviewer_keywords:
- MFC Add Class Wizard
- wizards [MFC]
ms.assetid: ad3b0989-d307-43b2-9417-3f9a78889024
caps.latest.revision: 16
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 4fafe461008e3545243d693e0d9e34acd57163e0
ms.openlocfilehash: 08d258c2b8386a4dd0c1d24c6ac6aa10f6c04a63
ms.contentlocale: fr-fr
ms.lasthandoff: 02/24/2017

---
# <a name="mfc-add-class-wizard"></a>Assistant Ajouter une classe MFC
Utilisez cet Assistant code pour ajouter une classe à un projet MFC existant, ou pour ajouter une classe à un projet ATL qui prend en charge MFC. Vous pouvez également ajouter des classes MFC à des projets Win32 prenant en charge MFC. Les fonctionnalités que vous avez spécifié lorsque vous avez créé votre projet déterminent les options disponibles dans cette boîte de dialogue.  
  
## <a name="names"></a>Noms  
 Dans cette page, spécifiez le nom de classe, la classe de base et les noms de fichier pour la nouvelle classe.  
  
 **Nom de classe**  
 Spécifie le nom de la nouvelle classe et fournit la base par défaut pour les noms des ID et des fichiers sur cette page. Les classes C++ commencent généralement « C », par exemple, « CMyClass » devient « Commencent », et ainsi de suite.  
  
 **Classe de base**  
 Spécifie le nom de la classe de base pour la nouvelle classe. Par défaut, la classe de base est [CWnd](../../mfc/reference/cwnd-class.md). La classe de base que vous sélectionnez détermine si les autres zones de cette page sont actives.  
  
 Le type de classe que vous définissez comme la classe de base détermine si la classe possède un ID de la boîte de dialogue ou un ID de ressource. Les types généraux de classes sont les suivantes :  
  
-   Classes telles que [CButton](../../mfc/reference/cbutton-class.md), [CWnd](../../mfc/reference/cwnd-class.md), ou [CDocument](../../mfc/reference/cdocument-class.md), qui ne nécessitent pas une boîte de dialogue ID ou ID de ressource. Ces classes n’utilisent pas un ID de boîte de dialogue ou de ressource. Si vous sélectionnez une de ces classes pour votre classe de base, le **ID de la boîte de dialogue** boîte et **ID de ressource DHTML** sont pas disponibles.  
  
-   Classes telles que [CDialog](../../mfc/reference/cdialog-class.md), [CFormView](../../mfc/reference/cformview-class.md), ou [CPropertyPage](../../mfc/reference/cpropertypage-class.md), qui nécessitent un ID de la boîte de dialogue.  
  
-   La classe [CDHtmlDialog](../../mfc/reference/cdhtmldialog-class.md), ce qui nécessite un ID de la boîte de dialogue, un ID de ressource DHTML et un nom de fichier HTML.  
  
 Pour les classes nécessitant un ID de la boîte de dialogue, vous pouvez trouver plus efficace d’utiliser la [éditeur de ressources](../../windows/resource-editors.md) pour créer la ressource de boîte de dialogue, assigner son ID dans la [fenêtre Propriétés](/visualstudio/ide/reference/properties-window), puis créez une classe associée à cet ID de ressource. Consultez la page [création d’une boîte de dialogue](../../windows/creating-a-new-dialog-box.md) pour plus d’informations sur la création d’une boîte de dialogue Windows standard.  
  
> [!NOTE]
>  Si vous commencez par créer une ressource de boîte de dialogue et que vous dérivez sa nouvelle classe de `CDHtmlDialog`, supprimer Windows standard **OK** et **Annuler** boutons qui apparaissent dans la boîte de dialogue par défaut. La boîte de dialogue Windows standard héberge le formulaire DHTML, qui contient son propre **OK** et **Annuler** boutons.  
  
 Bien que votre boîte de dialogue peut contenir des contrôles Windows et les contrôles DHTML, il n’est pas recommandé.  
  
 **ID de la boîte de dialogue**  
 Spécifie l’ID de la boîte de dialogue, si vous avez sélectionné `CDialog`, `CFormView`, `CPropertyPage`, ou `CDHtmlDialog` comme le **classe de Base**.  
  
 **fichier .h**  
 Définit le nom du fichier d’en-tête pour la nouvelle classe d’objet. Par défaut, ce nom est basé sur le nom que vous fournissez dans **nom de la classe**. Cliquez sur le bouton de sélection pour enregistrer le nom de fichier à l’emplacement de votre choix ou pour ajouter la déclaration de classe à un fichier existant. Si vous choisissez un fichier existant, l’Assistant l’enregistrera pas à l’emplacement sélectionné jusqu'à ce que vous cliquez sur **Terminer** dans l’Assistant.  
  
 L’Assistant n’écrase pas un fichier. Si vous sélectionnez le nom d’un fichier existant, cliquez sur **Terminer**, l’Assistant vous invite à indiquer si la déclaration de classe doit être ajoutée au contenu du fichier. Cliquez sur **Oui** pour ajouter le fichier ; cliquez sur **non** pour revenir à l’Assistant et spécifiez un autre nom de fichier.  
  
 **fichier .cpp**  
 Définit le nom du fichier d’implémentation pour la nouvelle classe d’objet. Par défaut, ce nom est basé sur le nom que vous fournissez dans **nom de la classe**. Cliquez sur le bouton de sélection pour enregistrer le nom de fichier à l’emplacement de votre choix. Le fichier n’est pas enregistré à l’emplacement sélectionné jusqu'à ce que vous cliquiez **Terminer** dans l’Assistant.  
  
 L’Assistant n’écrase pas un fichier. Si vous sélectionnez le nom d’un fichier existant, cliquez sur **Terminer**, l’Assistant vous invite à indiquer si l’implémentation de classe doit être ajoutée au contenu du fichier. Cliquez sur **Oui** pour ajouter le fichier ; cliquez sur **non** pour revenir à l’Assistant et spécifiez un autre nom de fichier.  
  
 **Active accessibility**  
 Active la prise en charge MFC pour Active Accessibility en appelant [EnableActiveAccessibility](../../mfc/reference/cwnd-class.md#enableactiveaccessibility) dans le constructeur. Cette option est disponible pour les classes dérivées de [CWnd](../../mfc/reference/cwnd-class.md).  
  
 **ID de ressource DHTML**  
 S’applique aux classes dérivées de `CDHtmlDialog` uniquement. Spécifie l’ID de ressource de la boîte de dialogue DHTML. L’ID de ressource s’affiche dans la section HTML du fichier .rc du projet, ainsi que le nom de fichier de boîte de dialogue HTML. La ressource DHTML, identifiée par cet ID, est hébergée par la boîte de dialogue, identifiée par **ID de la boîte de dialogue**.  
  
 **. Fichier HTM**  
 S’applique aux classes dérivées de `CDHtmlDialog` uniquement. Définit le nom du fichier HTML de la boîte de dialogue DHTML. Par défaut, ce nom de fichier est basé sur le nom de classe. Le nom du fichier apparaît dans la section HTML du fichier .rc du projet, ainsi que l’ID de ressource DHTML boîte de dialogue zone.  
  
 **Automation**  
 Définit le niveau de la classe de prise en charge de [Automation](../../mfc/automation.md). Automatisation au niveau de la classe est disponible pour toutes les classes qui prennent en charge Automation. Il est également disponible pour les projets créés avec la prise en charge pour l’automatisation. Autrement dit, soit un projet MFC qui [prend en charge ATL](../../atl/reference/mfc-support-in-atl-projects.md), ou un projet MFC pour lequel vous avez sélectionné le **Automation** case à cocher dans le [fonctionnalités avancées](../../mfc/reference/advanced-features-mfc-application-wizard.md) page de l’Assistant Application MFC.  
  
|Option|Description|  
|------------|-----------------|  
|**Aucun**|Indique ne qu’aucune prise en charge de l’Automation de la classe.|  
|**Automation**|Indique que la classe prend en charge Automation. Si vous sélectionnez cette option, la classe qui vient d’être créée est disponible en tant qu’objet programmable par les applications client Automation, tels que Microsoft Visual Basic et Microsoft Excel. Cette option n’est pas disponible pour les classes de base énumérées après ce tableau.|  
|**Qui peut être créé par ID de type**|Indique que la classe et le projet prennent en charge les autres applications créant des objets de cette classe à l’aide d’Automation. Avec cette option, les clients automation peuvent créer directement un objet Automation. L’ID de type dans la zone de texte est utilisé par l’application cliente pour spécifier l’objet à créer ; Il est au niveau du système et doit être unique. Cette option n’est pas disponible pour les classes de base énumérées après ce tableau.|  
  
 Prise en charge Automation n’est pas disponible pour les classes de base suivantes :  
  
-   `CAsyncMonitorFile`  
  
-   `CAsyncSocket`  
  
-   `CCachedDataPathProperty`  
  
-   `CConnectionPoint`  
  
-   `CDatabase`  
  
-   `CDataPathProperty`  
  
-   `CHttpFilter`  
  
-   `CHttpServer`  
  
-   `CInternetSession`  
  
-   `CObject`  
  
-   `CSocket`  
  
 **ID du type**  
 Définit l’ID du type de la classe. Le **ID de Type** zone concatène le nom du projet et le nouveau nom de classe comme suit : *MFCProj.MFCClass*. Cet ID est modifiable uniquement si vous avez sélectionné le **Automation** option **Création possible par ID de type**.  
  
 **Générer des ressources DocTemplate**  
 Indique que les documents créés par l’application dispose de ressources de modèle de document. Pour activer cette case à cocher, le projet doit prendre en charge l’architecture document/vue MFC et la classe de base de cette classe doit être [CFormView](../../mfc/reference/cformview-class.md).  
  
 Consultez la page [modèles de Document et le processus de création de Document/vue](../../mfc/document-templates-and-the-document-view-creation-process.md) pour plus d’informations.  
  
## <a name="see-also"></a>Voir aussi  
 [Classe MFC](../../mfc/reference/adding-an-mfc-class.md)   
 [Ajout d’une classe](../../ide/adding-a-class-visual-cpp.md)

