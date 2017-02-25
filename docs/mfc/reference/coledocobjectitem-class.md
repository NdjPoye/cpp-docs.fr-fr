---
title: "COleDocObjectItem Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "COleDocObjectItem"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COleDocObjectItem class"
  - "containment"
  - "containment, doc object"
  - "doc object containment"
  - "document object containment"
ms.assetid: d150d306-8fd3-4831-b06d-afbe71d8fc9b
caps.latest.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 25
---
# COleDocObjectItem Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Relation contenant\-contenu de document actif d'outils.  
  
## Syntaxe  
  
```  
class COleDocObjectItem : public COleClientItem  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[COleDocObjectItem::COleDocObjectItem](../Topic/COleDocObjectItem::COleDocObjectItem.md)|Crée un élément d' `COleDocObject` .|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[COleDocObjectItem::DoDefaultPrinting](../Topic/COleDocObjectItem::DoDefaultPrinting.md)|Imprime le document de l'application conteneur à l'aide de les paramètres d'imprimante par défaut.|  
|[COleDocObjectItem::ExecCommand](../Topic/COleDocObjectItem::ExecCommand.md)|Exécute la commande spécifiée par l'utilisateur.|  
|[COleDocObjectItem::GetActiveView](../Topic/COleDocObjectItem::GetActiveView.md)|Extrait la vue active du document.|  
|[COleDocObjectItem::GetPageCount](../Topic/COleDocObjectItem::GetPageCount.md)|Récupère le nombre de pages dans le document de l'application conteneur.|  
|[COleDocObjectItem::OnPreparePrinting](../Topic/COleDocObjectItem::OnPreparePrinting.md)|Prépare le document de l'application conteneur pour l'impression.|  
|[COleDocObjectItem::OnPrint](../Topic/COleDocObjectItem::OnPrint.md)|Imprime le document de l'application conteneur.|  
|[COleDocObjectItem::QueryCommand](../Topic/COleDocObjectItem::QueryCommand.md)|Requêtes pour l'état d'une ou plusieurs commandes générées par les événements d'interface utilisateur.|  
|[COleDocObjectItem::Release](../Topic/COleDocObjectItem::Release.md)|Libère la connexion à un élément OLE lié et la batterie si elle a été ouverte.  Ne supprime pas l'élément client.|  
  
## Notes  
 Dans MFC, un document actif est traité de la même façon à un arial regular, incorporer modifiable sur place, avec les différences suivantes :  
  
-   `COleDocument`\- la classe dérivée maintient toujours une liste des éléments actuellement incorporés ; toutefois, ces éléments peuvent être `COleDocObjectItem`\- éléments dérivés.  
  
-   Lorsqu'un document actif est actif, il occupe la zone cliente entière de la vue lorsqu'il est actif sur place.  
  
-   Un conteneur de documents actifs avez le contrôle total du menu de **Aide** .  
  
-   Le menu de **Aide** contient des éléments de menu pour le conteneur de documents actifs et le serveur.  
  
 Étant donné que le conteneur de documents actifs détient le menu de **Aide** , le conteneur est chargé de transférer des messages de menu de **Aide** de serveur au serveur.  Cette intégration est gérée par `COleDocObjectItem`.  
  
 Pour plus d'informations sur la fusion de menus et le lancement du document actif, consultez la vue d'ensemble de [Relation contenant\-contenu de Document actif](../../mfc/active-document-containment.md).  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CDocItem](../../mfc/reference/cdocitem-class.md)  
  
 [COleClientItem](../../mfc/reference/coleclientitem-class.md)  
  
 `COleDocObjectItem`  
  
## Configuration requise  
 **Header:** afxole.h  
  
## Voir aussi  
 [MFC exemple MFCBIND](../../top/visual-cpp-samples.md)   
 [COleClientItem Class](../../mfc/reference/coleclientitem-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [COleClientItem Class](../../mfc/reference/coleclientitem-class.md)   
 [CDocObjectServerItem Class](../../mfc/reference/cdocobjectserveritem-class.md)