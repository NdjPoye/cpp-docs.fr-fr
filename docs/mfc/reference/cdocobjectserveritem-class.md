---
title: Classe de CDocObjectServerItem | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDocObjectServerItem
- AFXDOCOB/CDocObjectServerItem
- AFXDOCOB/CDocObjectServerItem::CDocObjectServerItem
- AFXDOCOB/CDocObjectServerItem::GetDocument
- AFXDOCOB/CDocObjectServerItem::OnHide
- AFXDOCOB/CDocObjectServerItem::OnShow
dev_langs:
- C++
helpviewer_keywords:
- document object server
- CDocObjectServerItem class
- servers [C++], ActiveX documents
- docobject server
- servers [C++], doc objects
- ActiveX documents [C++], document server
ms.assetid: 530f7156-50c8-4806-9328-602c9133f622
caps.latest.revision: 22
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 06cf873512fbf43b729d9a70f185582a4e48cafc
ms.contentlocale: fr-fr
ms.lasthandoff: 02/24/2017

---
# <a name="cdocobjectserveritem-class"></a>CDocObjectServerItem (classe)
Implémente les verbes de serveur OLE , en particulier pour les serveurs DocObject.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CDocObjectServerItem : public COleServerItem  
```  
  
## <a name="members"></a>Membres  
  
### <a name="protected-constructors"></a>Constructeurs protégés  
  
|Nom|Description|  
|----------|-----------------|  
|[CDocObjectServerItem::CDocObjectServerItem](#cdocobjectserveritem)|Construit un objet `CDocObjectServerItem`.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CDocObjectServerItem::GetDocument](#getdocument)|Récupère un pointeur vers le document qui contient l’élément.|  
  
### <a name="protected-methods"></a>Méthodes protégées  
  
|Nom|Description|  
|----------|-----------------|  
|[CDocObjectServerItem::OnHide](#onhide)|Lève une exception si le framework tente de masquer un élément DocObject.|  
|[CDocObjectServerItem::OnShow](#onshow)|Appelé par l’infrastructure pour rendre le DocObject place élément actif. Si l’élément n’est pas un DocObject, appelle [COleServerItem::OnShow](../../mfc/reference/coleserveritem-class.md#onshow).|  
  
## <a name="remarks"></a>Remarques  
 `CDocObjectServerItem`définit les fonctions membres substituables : [OnHide](#onhide), [OnOpen](http://msdn.microsoft.com/en-us/7a9b1363-6ad8-4732-9959-4e35c07644fd), et [OnShow](#onshow).  
  
 Pour utiliser `CDocObjectServerItem`, s’assurer que les [OnGetEmbeddedItem](../../mfc/reference/coleserverdoc-class.md#ongetembeddeditem) remplacer dans votre `COleServerDoc`-classe dérivée retourne un nouveau `CDocObjectServerItem` objet. Si vous devez modifier toutes les fonctionnalités de votre élément, vous pouvez créer une nouvelle instance de votre propre `CDocObjectServerItem`-classe dérivée.  
  
 Pour plus d’informations sur DocObjects, consultez [CDocObjectServer](../../mfc/reference/cdocobjectserver-class.md) et [COleCmdUI](../../mfc/reference/colecmdui-class.md) dans les *référence MFC*. Consultez également [Internet premières étapes : Documents actifs](../../mfc/active-documents-on-the-internet.md) et [Documents actifs](../../mfc/active-documents-on-the-internet.md).  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CDocItem](../../mfc/reference/cdocitem-class.md)  
  
 [COleServerItem](../../mfc/reference/coleserveritem-class.md)  
  
 `CDocObjectServerItem`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxdocob.h  
  
##  <a name="cdocobjectserveritem"></a>CDocObjectServerItem::CDocObjectServerItem  
 Construit un objet `CDocObjectServerItem`.  
  
```  
CDocObjectServerItem(COleServerDoc* pServerDoc, BOOL bAutoDelete);
```  
  
### <a name="parameters"></a>Paramètres  
 `pServerDoc`  
 Pointeur vers le document qui contient le nouvel élément DocObject.  
  
 `bAutoDelete`  
 Indique si l’objet peut être supprimé lors de la publication d’un lien vers celle-ci. Attribuez à l’argument **FALSE** si le `CDocObjectServerItem` objet fait partie intégrante des données de votre document. Affectez-lui la valeur **TRUE** si l’objet est une structure secondaire utilisée pour identifier une plage de données de votre document qui peuvent être supprimées par l’infrastructure.  
  
##  <a name="getdocument"></a>CDocObjectServerItem::GetDocument  
 Récupère un pointeur vers le document qui contient l’élément.  
  
```  
COleServerDoc* GetDocument() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Un pointeur vers le document qui contient l’élément ; **NULL** si l’élément ne fait pas partie d’un document.  
  
### <a name="remarks"></a>Notes  
 Cela permet l’accès au document serveur que vous avez passé comme argument à la [CDocObjectServerItem](#cdocobjectserveritem) constructeur.  
  
##  <a name="onhide"></a>CDocObjectServerItem::OnHide  
 Appelé par l’infrastructure pour masquer l’élément.  
  
```  
virtual void OnHide();
```  
  
### <a name="remarks"></a>Notes  
 L’implémentation par défaut lève une exception si l’élément est un DocObject. Vous ne pouvez pas masquer un élément de DocObject actif parce qu’il prend toute la vue. Vous devez désactiver l’élément DocObject pour la faire disparaître. Si l’élément n’est pas un DocObject, l’implémentation par défaut appelle [COleServerItem::OnHide](../../mfc/reference/coleserveritem-class.md#onhide).  
  
##  <a name="onshow"></a>CDocObjectServerItem::OnShow  
 Appelé par l’infrastructure pour demander à l’application serveur pour rendre le DocObject place élément actif.  
  
```  
virtual void OnShow();
```  
  
### <a name="remarks"></a>Remarques  
 Si l’élément n’est pas un DocObject, l’implémentation par défaut appelle [COleServerItem::OnShow](../../mfc/reference/coleserveritem-class.md#onopen). Remplacez cette fonction si vous souhaitez effectuer un traitement lors de l’ouverture d’un élément DocObject particulier.  
  
## <a name="see-also"></a>Voir aussi  
 [Classe COleServerItem](../../mfc/reference/coleserveritem-class.md)   
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)   
 [CDocObjectServer (classe)](../../mfc/reference/cdocobjectserver-class.md)   
 [Classe COleDocObjectItem](../../mfc/reference/coledocobjectitem-class.md)

