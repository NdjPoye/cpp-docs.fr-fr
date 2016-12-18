---
title: "CMultiDocTemplate Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMultiDocTemplate"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMultiDocTemplate class"
  - "MDI, modèle"
ms.assetid: 5b8aa328-e461-41d0-b388-00594535e119
caps.latest.revision: 21
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMultiDocTemplate Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Définit un modèle de document qui implémente l'interface multidocument \(MDI\).  
  
## Syntaxe  
  
```  
  
class CMultiDocTemplate : public CDocTemplate  
  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CMultiDocTemplate::CMultiDocTemplate](../Topic/CMultiDocTemplate::CMultiDocTemplate.md)|Construit un objet `CMultiDocTemplate`.|  
  
## Notes  
 Une application MDI utilise la fenêtre frame principale comme un espace de travail dans lequel l'utilisateur peut ouvrir plusieurs fenêtres frames de document ou plus, qui affiche un document.  Pour une description plus détaillée MDI, consultez *les indications d'interface Windows pour la conception de logiciels*.  
  
 Un modèle de document définit les relations entre trois types de classes :  
  
-   Une classe de document, que vous dérivez de [CDocument](../../mfc/reference/cdocument-class.md).  
  
-   Une classe d'affichage, qui affiche des données provenant de la classe de document listé en haut.  Vous pouvez dériver cette classe de [CView](../../mfc/reference/cview-class.md), d' `CScrollView`, d' `CFormView`, ou d' `CEditView`.  \(Vous pouvez également utiliser `CEditView` directement.\)  
  
-   Une classe de fenêtre frame, qui contient la vue.  Pour un modèle de documents MDI, vous pouvez dériver cette classe d' `CMDIChildWnd`, ou, si vous n'avez pas besoin de personnaliser le comportement des fenêtres frames de le document, vous pouvez utiliser [CMDIChildWnd](../../mfc/reference/cmdichildwnd-class.md) directement sans dériver votre propre classe.  
  
 Une application MDI peut prendre en charge plusieurs types de document, et les documents de différents types peuvent être ouvertes simultanément.  Votre application possède un modèle de document pour chaque type de document prise en charge.  Par exemple, si vos documents et feuilles texte de l'application prend en charge MDI, l'application a deux objets d' `CMultiDocTemplate` .  
  
 L'application utilise le modèle de document lorsque l'utilisateur crée un document.  Si plusieurs types de prises en charge des applications de document, l'infrastructure obtient les noms des types de document pris en charge des modèles de document et les affiche dans une liste de la boîte de dialogue nouveau fichier.  Une fois que l'utilisateur a sélectionné un type de document, l'application crée un objet de classe de document, un objet de fenêtre frame, et un objet de vue et des liens entre eux.  
  
 Vous n'avez pas besoin de n'appeler une fonction membre d' `CMultiDocTemplate` à l'exception de le constructeur.  L'infrastructure gère les objets d' `CMultiDocTemplate` en interne.  
  
 Pour plus d'informations sur `CMultiDocTemplate`, consultez [Modèles de document et le processus de création du document\/vue](../../mfc/document-templates-and-the-document-view-creation-process.md).  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CDocTemplate](../../mfc/reference/cdoctemplate-class.md)  
  
 `CMultiDocTemplate`  
  
## Configuration requise  
 **En\-tête :** afxwin.h  
  
## Voir aussi  
 [CDocTemplate Class](../../mfc/reference/cdoctemplate-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [CDocTemplate Class](../../mfc/reference/cdoctemplate-class.md)   
 [CSingleDocTemplate Class](../../mfc/reference/csingledoctemplate-class.md)   
 [CWinApp Class](../../mfc/reference/cwinapp-class.md)