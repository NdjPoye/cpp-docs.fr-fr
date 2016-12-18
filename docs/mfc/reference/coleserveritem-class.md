---
title: "COleServerItem Class | Microsoft Docs"
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
  - "COleServerItem"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COleServerItem class"
  - "applications serveur OLE, managing server documents"
  - "applications serveur OLE, server interfaces"
  - "OLE server documents"
  - "serveurs, OLE"
ms.assetid: 80256df6-3888-4256-944b-787d4b2e6b0d
caps.latest.revision: 23
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# COleServerItem Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Fournit l'interface du serveur à OLE éléments.  
  
## Syntaxe  
  
```  
class COleServerItem : public CDocItem  
```  
  
## Membres  
  
### Constructeurs protégés  
  
|Nom|Description|  
|---------|-----------------|  
|[COleServerItem::COleServerItem](../Topic/COleServerItem::COleServerItem.md)|Construit un objet `COleServerItem`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[COleServerItem::AddOtherClipboardData](../Topic/COleServerItem::AddOtherClipboardData.md)|Les formats de présentation et de conversion d'emplacements dans `COleDataSource` objet.|  
|[COleServerItem::CopyToClipboard](../Topic/COleServerItem::CopyToClipboard.md)|Copie l'élément dans le presse\-papiers.|  
|[COleServerItem::DoDragDrop](../Topic/COleServerItem::DoDragDrop.md)|Effectue une opération de glisser\-déplacer.|  
|[COleServerItem::GetClipboardData](../Topic/COleServerItem::GetClipboardData.md)|Obtient la source de données à utiliser dans le transfert de données \(glisser\-déplacer ou le presse\-papiers\).|  
|[COleServerItem::GetDocument](../Topic/COleServerItem::GetDocument.md)|Retourne le document serveur qui contient l'élément.|  
|[COleServerItem::GetEmbedSourceData](../Topic/COleServerItem::GetEmbedSourceData.md)|Obtient les données de **CF\_EMBEDSOURCE** pour un élément OLE.|  
|[COleServerItem::GetItemName](../Topic/COleServerItem::GetItemName.md)|Retourne le nom de l'élément.  Utilisé pour les éléments liés uniquement.|  
|[COleServerItem::GetLinkSourceData](../Topic/COleServerItem::GetLinkSourceData.md)|Obtient les données d' `CF_LINKSOURCE` pour un élément OLE.|  
|[COleServerItem::GetObjectDescriptorData](../Topic/COleServerItem::GetObjectDescriptorData.md)|Obtient les données de **CF\_OBJECTDESCRIPTOR** pour un élément OLE.|  
|[COleServerItem::IsConnected](../Topic/COleServerItem::IsConnected.md)|Indique si l'élément est actif lié à un conteneur actif.|  
|[COleServerItem::IsLinkedItem](../Topic/COleServerItem::IsLinkedItem.md)|Indique si l'élément représente un élément OLE lié.|  
|[COleServerItem::NotifyChanged](../Topic/COleServerItem::NotifyChanged.md)|Gère tous les conteneurs avec la mise à jour de liaison automatique.|  
|[COleServerItem::OnDoVerb](../Topic/COleServerItem::OnDoVerb.md)|Appelé pour effectuer un verbe.|  
|[COleServerItem::OnDraw](../Topic/COleServerItem::OnDraw.md)|Appelée lorsque les demandes de conteneur de dessiner l'élément ; implémentation requise.|  
|[COleServerItem::OnDrawEx](../Topic/COleServerItem::OnDrawEx.md)|Appelé pour le dessin spécialisé d'élément.|  
|[COleServerItem::OnGetClipboardData](../Topic/COleServerItem::OnGetClipboardData.md)|Appelé par l'infrastructure pour obtenir les données qui seraient copiées dans le presse\-papiers.|  
|[COleServerItem::OnGetExtent](../Topic/COleServerItem::OnGetExtent.md)|Appelé par l'infrastructure pour récupérer la taille du élément OLE.|  
|[COleServerItem::OnInitFromData](../Topic/COleServerItem::OnInitFromData.md)|Appelé par l'infrastructure pour initialiser un élément OLE à l'aide de le contenu de l'objet de transfert de données spécifié.|  
|[COleServerItem::OnQueryUpdateItems](../Topic/COleServerItem::OnQueryUpdateItems.md)|Appelé pour déterminer si les éléments liés requièrent mettre à jour.|  
|[COleServerItem::OnRenderData](../Topic/COleServerItem::OnRenderData.md)|Récupère les données dans le cadre de le rendu différé.|  
|[COleServerItem::OnRenderFileData](../Topic/COleServerItem::OnRenderFileData.md)|Récupère les données dans un objet d' `CFile` dans le cadre de le rendu différé.|  
|[COleServerItem::OnRenderGlobalData](../Topic/COleServerItem::OnRenderGlobalData.md)|Récupère les données dans `HGLOBAL` dans le cadre de le rendu différé.|  
|[COleServerItem::OnSetColorScheme](../Topic/COleServerItem::OnSetColorScheme.md)|Appelé pour définir le modèle de couleurs de l'élément.|  
|[COleServerItem::OnSetData](../Topic/COleServerItem::OnSetData.md)|Appelé pour définir les données de l'élément.|  
|[COleServerItem::OnSetExtent](../Topic/COleServerItem::OnSetExtent.md)|Appelé par l'infrastructure pour définir la taille de l'élément OLE.|  
|[COleServerItem::OnUpdate](../Topic/COleServerItem::OnUpdate.md)|Appelé lorsqu'une partie du document l'élément appartient dans est modifié.|  
|[COleServerItem::OnUpdateItems](../Topic/COleServerItem::OnUpdateItems.md)|Appelée pour mettre à jour le cache de présentation de tous les éléments du document serveur.|  
|[COleServerItem::SetItemName](../Topic/COleServerItem::SetItemName.md)|Définit le nom de l'élément.  Utilisé pour les éléments liés uniquement.|  
  
### Méthodes protégées  
  
|Nom|Description|  
|---------|-----------------|  
|[COleServerItem::GetDataSource](../Topic/COleServerItem::GetDataSource.md)|Obtient l'objet permet aux formats de conversion de mémoire.|  
|[COleServerItem::OnHide](../Topic/COleServerItem::OnHide.md)|Appelé par l'infrastructure pour masquer un élément OLE.|  
|[COleServerItem::OnOpen](../Topic/COleServerItem::OnOpen.md)|Appelé par l'infrastructure pour afficher un élément OLE dans sa propre fenêtre de niveau supérieur.|  
|[COleServerItem::OnShow](../Topic/COleServerItem::OnShow.md)|Appelée lorsque les demandes de conteneur pour afficher l'élément.|  
  
### Données membres publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[COleServerItem::m\_sizeExtent](../Topic/COleServerItem::m_sizeExtent.md)|Demande au serveur sur la partie du élément OLE est visible.|  
  
## Notes  
 Un élément lié peut représenter une partie ou la totalité du document serveur.  Un élément inline représente toujours un document serveur complet.  
  
 La classe d' `COleServerItem` définit plusieurs fonctions membres substituables qui sont appelées par OLE des bibliothèques de liens dynamiques \(DLLs\) du système, habituellement en réponse à les demandes de l'application conteneur.  Ces fonctions membres permettent l'application conteneur de manipuler l'élément indirectement de plusieurs façons, par exemple par l'afficher, exécuter les verbes, ou récupérer ses données dans différents formats.  
  
 Pour utiliser `COleServerItem`, dérivez une classe de celle\-ci et implémentez les fonctions membres d' [OnDraw](../Topic/COleServerItem::OnDraw.md) et de [sérialisez](../Topic/CObject::Serialize.md) .  La fonction d' `OnDraw` fournit une représentation de métafichier d'un élément, l'activation d'afficher lorsqu'une application conteneur ouvre un document composite.  La fonction d' `Serialize` d' `CObject` fournit les performances native d'un élément, ce qui permet un élément inline à transférer entre le serveur et les applications conteneur.  [OnGetExtent](../Topic/COleServerItem::OnGetExtent.md) fournit la taille naturelle de l'élément au conteneur, permettant au conteneur de dimensionner l'élément.  
  
 Pour plus d'informations sur les serveurs et les rubriques connexes, consultez l'article [serveurs : implémenter un serveur](../../mfc/servers-implementing-a-server.md) et « créer une application conteneur\/serveur » dans l'article [conteneurs : Fonctionnalités avancées](../../mfc/containers-advanced-features.md).  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CDocItem](../../mfc/reference/cdocitem-class.md)  
  
 `COleServerItem`  
  
## Configuration requise  
 **Header:** afxole.h  
  
## Voir aussi  
 [exemple MFC HIERSVR](../../top/visual-cpp-samples.md)   
 [CDocItem Class](../../mfc/reference/cdocitem-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [COleClientItem Class](../../mfc/reference/coleclientitem-class.md)   
 [COleServerDoc Class](../../mfc/reference/coleserverdoc-class.md)   
 [COleTemplateServer Class](../../mfc/reference/coletemplateserver-class.md)