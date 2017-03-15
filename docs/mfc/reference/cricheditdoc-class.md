---
title: CRichEditDoc (classe) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CRichEditDoc
dev_langs:
- C++
helpviewer_keywords:
- document/view architecture, rich edit controls
- OLE containers, rich edit
- documents, rich edit
- rich edit controls, OLE container
- CRichEditDoc class
ms.assetid: c936ec18-d516-49d4-b7fb-c9aa0229eddc
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: c7233c27c92c6dc689853e1913bb26f0bb5941fa
ms.lasthandoff: 02/24/2017

---
# <a name="cricheditdoc-class"></a>CRichEditDoc (classe)
Avec [CRichEditView](../../mfc/reference/cricheditview-class.md) et [CRichEditCntrItem](../../mfc/reference/cricheditcntritem-class.md), fournit les fonctionnalités du contrôle RichEdit dans le contexte de l’architecture document/vue de MFC.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CRichEditDoc : public COleServerDoc  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CRichEditDoc::CreateClientItem](#createclientitem)|Appelée pour effectuer un nettoyage du document.|  
|[CRichEditDoc::GetStreamFormat](#getstreamformat)|Indique si les flux d’entrée et sortie doivent inclure des informations de format.|  
|[CRichEditDoc::GetView](#getview)|Récupère l’associé [CRichEditView](../../mfc/reference/cricheditview-class.md) objet.|  
  
### <a name="public-data-members"></a>Membres de données publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CRichEditDoc::m_bRTF](#m_brtf)|Indique si le flux d’e/s doit inclure la mise en forme.|  
  
## <a name="remarks"></a>Remarques  
 Un « contrôle rich edit » est une fenêtre dans laquelle l’utilisateur peut entrer et modifier du texte. Le texte peut être attribué caractères ou paragraphes et peut inclure des objets OLE incorporés. Les contrôles RichEdit fournissent une interface de programmation pour la mise en forme de texte. Toutefois, une application doit implémenter tous les composants d’interface utilisateur nécessaires pour rendre les opérations de mise en forme disponibles à l’utilisateur.  
  
 `CRichEditView`conserve le texte et les caractéristiques de mise en forme du texte. `CRichEditDoc`gère la liste des éléments de clients qui se trouvent dans la vue. `CRichEditCntrItem`fournit un accès côté conteneur pour les éléments clients OLE.  
  
 Ce contrôle commun de Windows (et par conséquent la [CRichEditCtrl](../../mfc/reference/cricheditctrl-class.md) et les classes associées) est disponible uniquement pour les programmes s’exécutant sous Windows 95/98 et Windows NT versions 3.51 et ultérieures.  
  
 Pour obtenir un exemple de l’utilisation d’un document RichEdit dans une application MFC, consultez la [WORDPAD](../../visual-cpp-samples.md) exemple d’application.  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CDocument](../../mfc/reference/cdocument-class.md)  
  
 [COleDocument](../../mfc/reference/coledocument-class.md)  
  
 [COleLinkingDoc plutôt](../../mfc/reference/colelinkingdoc-class.md)  
  
 [COleServerDoc](../../mfc/reference/coleserverdoc-class.md)  
  
 `CRichEditDoc`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxrich.h  
  
##  <a name="a-namecreateclientitema--cricheditdoccreateclientitem"></a><a name="createclientitem"></a>CRichEditDoc::CreateClientItem  
 Appelez cette fonction pour créer un `CRichEditCntrItem` de l’objet et l’ajouter à ce document.  
  
```  
virtual CRichEditCntrItem* CreateClientItem(REOBJECT* preo = NULL) const = 0;  
```  
  
### <a name="parameters"></a>Paramètres  
 *preo*  
 Pointeur vers un [REOBJECT](http://msdn.microsoft.com/library/windows/desktop/bb787946) structure qui décrit un élément OLE. La nouvelle `CRichEditCntrItem` objet est construit autour de cet objet OLE. Si *preo* est **NULL**, le nouvel élément client est vide.  
  
### <a name="return-value"></a>Valeur de retour  
 Pointeur vers une nouvelle [CRichEditCntrItem](../../mfc/reference/cricheditcntritem-class.md) objet qui a été ajouté à ce document.  
  
### <a name="remarks"></a>Notes  
 Cette fonction effectue une initialisation d’OLE.  
  
 Pour plus d’informations, consultez la [REOBJECT](http://msdn.microsoft.com/library/windows/desktop/bb787946) de la structure dans le [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegetstreamformata--cricheditdocgetstreamformat"></a><a name="getstreamformat"></a>CRichEditDoc::GetStreamFormat  
 Appelez cette fonction pour déterminer le format du texte pour le contenu de l’édition enrichie de diffusion en continu.  
  
```  
int GetStreamFormat() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Un des indicateurs suivants :  
  
- `SF_TEXT`Indique que le contrôle rich edit ne conserve pas les informations de mise en forme.  
  
- `SF_RTF`Indique que le contrôle rich edit ne conserve pas les informations de mise en forme.  
  
### <a name="remarks"></a>Remarques  
 La valeur de retour est basée sur le [m_bRTF](#m_brtf) membre de données. Cette fonction retourne `SF_RTF` si `m_bRTF` est **TRUE**; sinon, `SF_TEXT`.  
  
##  <a name="a-namegetviewa--cricheditdocgetview"></a><a name="getview"></a>CRichEditDoc::GetView  
 Appelez cette fonction pour accéder à la [CRichEditView](../../mfc/reference/cricheditview-class.md) objet associé à ce `CRichEditDoc` objet.  
  
```  
virtual CRichEditView* GetView() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Pointeur vers le `CRichEditView` objet associé au document.  
  
### <a name="remarks"></a>Notes  
 Le texte et les informations de mise en forme sont contenus dans le `CRichEditView` objet. Le `CRichEditDoc` objet gère les éléments OLE pour la sérialisation. Il doit y avoir qu’un seul `CRichEditView` pour chaque `CRichEditDoc`.  
  
##  <a name="a-namembrtfa--cricheditdocmbrtf"></a><a name="m_brtf"></a>CRichEditDoc::m_bRTF  
 Lors de la **TRUE**, indique que [CRichEditCtrl::StreamIn](../../mfc/reference/cricheditctrl-class.md#streamin) et [CRichEditCtrl::StreamOut](../../mfc/reference/cricheditctrl-class.md#streamout) doit stocker paragraphe et les caractéristiques de mise en forme des caractères.  
  
```  
BOOL m_bRTF;  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Exemple MFC WORDPAD](../../visual-cpp-samples.md)   
 [Classe de COleServerDoc](../../mfc/reference/coleserverdoc-class.md)   
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)   
 [CRichEditView (classe)](../../mfc/reference/cricheditview-class.md)   
 [CRichEditCntrItem (classe)](../../mfc/reference/cricheditcntritem-class.md)   
 [COleDocument (classe)](../../mfc/reference/coledocument-class.md)   
 [CRichEditCtrl (classe)](../../mfc/reference/cricheditctrl-class.md)

