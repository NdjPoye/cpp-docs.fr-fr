---
title: Classe de CRichEditCntrItem | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CRichEditCntrItem
- AFXRICH/CRichEditCntrItem
- AFXRICH/CRichEditCntrItem::CRichEditCntrItem
- AFXRICH/CRichEditCntrItem::SyncToRichEditObject
dev_langs:
- C++
helpviewer_keywords:
- CRichEditCntrItem class
- OLE items, in rich edit views
- rich edit controls, using
- rich edit controls, OLE items
ms.assetid: 6c0b4efe-0fb8-4621-b5e1-fdcb8ec48c3b
caps.latest.revision: 24
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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: b29c7c3b80d24ef9ddb94e09c6b5c7bf2444bb4f
ms.lasthandoff: 02/24/2017

---
# <a name="cricheditcntritem-class"></a>CRichEditCntrItem (classe)
Avec [CRichEditView](../../mfc/reference/cricheditview-class.md) et [CRichEditDoc](../../mfc/reference/cricheditdoc-class.md), fournit les fonctionnalités du contrôle RichEdit dans le contexte de l’architecture document/vue de MFC.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CRichEditCntrItem : public COleClientItem  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CRichEditCntrItem::CRichEditCntrItem](#cricheditcntritem)|Construit un objet `CRichEditCntrItem`.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CRichEditCntrItem::SyncToRichEditObject](#synctoricheditobject)|Active l’élément dans un autre type.|  
  
## <a name="remarks"></a>Remarques  
 Un « contrôle rich edit » est une fenêtre dans laquelle l’utilisateur peut entrer et modifier du texte. Le texte peut être attribué caractères ou paragraphes et peut inclure des objets OLE incorporés. Les contrôles RichEdit fournissent une interface de programmation pour la mise en forme de texte. Toutefois, une application doit implémenter tous les composants d’interface utilisateur nécessaires pour rendre les opérations de mise en forme disponibles à l’utilisateur.  
  
 `CRichEditView`conserve le texte et les caractéristiques de mise en forme du texte. `CRichEditDoc`gère la liste des éléments client OLE dans la vue. `CRichEditCntrItem`fournit un accès côté conteneur à l’élément client OLE.  
  
 Ce contrôle commun de Windows (et par conséquent la [CRichEditCtrl](../../mfc/reference/cricheditctrl-class.md) et les classes associées) est disponible uniquement pour les programmes s’exécutant sous Windows 95/98 et Windows NT versions 3.51 et ultérieures.  
  
 Pour obtenir un exemple d’utilisation des éléments de conteneur d’édition enrichi dans une application MFC, consultez la [WORDPAD](../../visual-cpp-samples.md) exemple d’application.  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CDocItem](../../mfc/reference/cdocitem-class.md)  
  
 [COleClientItem](../../mfc/reference/coleclientitem-class.md)  
  
 `CRichEditCntrItem`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxrich.h  
  
##  <a name="cricheditcntritem"></a>CRichEditCntrItem::CRichEditCntrItem  
 Appelez cette fonction pour créer un `CRichEditCntrItem` de l’objet et l’ajouter au document conteneur.  
  
```  
CRichEditCntrItem(
    REOBJECT* preo = NULL,  
    CRichEditDoc* pContainer = NULL);
```  
  
### <a name="parameters"></a>Paramètres  
 *preo*  
 Pointeur vers un [REOBJECT](http://msdn.microsoft.com/library/windows/desktop/bb787946) structure qui décrit un élément OLE. La nouvelle `CRichEditCntrItem` objet est construit autour de cet objet OLE. Si *preo* est **NULL**, l’élément client est vide.  
  
 `pContainer`  
 Pointeur vers le document conteneur qui contient cet élément. Si `pContainer` est **NULL**, vous devez appeler explicitement [COleDocument::AddItem](../../mfc/reference/coledocument-class.md#additem) pour ajouter cet élément de client à un document.  
  
### <a name="remarks"></a>Remarques  
 Cette fonction effectue une initialisation d’OLE.  
  
 Pour plus d’informations, consultez la [REOBJECT](http://msdn.microsoft.com/library/windows/desktop/bb787946) de la structure dans le [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="synctoricheditobject"></a>CRichEditCntrItem::SyncToRichEditObject  
 Appelez cette fonction pour synchroniser l’aspect de l’appareil, [DVASPECT](http://msdn.microsoft.com/library/windows/desktop/ms690318), cela **CRichEditCntrltem** à celle spécifiée par *REO ne possèdent*.  
  
```  
void SyncToRichEditObject(REOBJECT& reo);
```  
  
### <a name="parameters"></a>Paramètres  
 *REO ne possèdent*  
 Référence à un [REOBJECT](http://msdn.microsoft.com/library/windows/desktop/bb787946) structure qui décrit un élément OLE.  
  
### <a name="remarks"></a>Remarques  
 Pour plus d’informations, consultez [DVASPECT](http://msdn.microsoft.com/library/windows/desktop/ms690318) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## <a name="see-also"></a>Voir aussi  
 [Exemple MFC WORDPAD](../../visual-cpp-samples.md)   
 [Classe de COleClientItem](../../mfc/reference/coleclientitem-class.md)   
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)   
 [CRichEditDoc (classe)](../../mfc/reference/cricheditdoc-class.md)   
 [CRichEditView (classe)](../../mfc/reference/cricheditview-class.md)

