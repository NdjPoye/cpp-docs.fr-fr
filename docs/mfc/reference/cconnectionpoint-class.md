---
title: "CConnectionPoint Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CConnectionPoint"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CConnectionPoint class"
ms.assetid: f0f23a1e-5e8c-41a9-aa6c-1a4793b28e8f
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 21
---
# CConnectionPoint Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Définit un type particulier d'interface utilisé pour communiquer avec d'autres objets OLE, appelé « point de connexion. »  
  
## Syntaxe  
  
```  
class CConnectionPoint : public CCmdTarget  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CConnectionPoint::CConnectionPoint](../Topic/CConnectionPoint::CConnectionPoint.md)|Construit un objet `CConnectionPoint`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CConnectionPoint::GetConnections](../Topic/CConnectionPoint::GetConnections.md)|Récupère tous les points de connexion dans un mappage de connexions.|  
|[CConnectionPoint::GetContainer](../Topic/CConnectionPoint::GetContainer.md)|Récupère le conteneur du contrôle qui possède le mappage de connexions.|  
|[CConnectionPoint::GetIID](../Topic/CConnectionPoint::GetIID.md)|Récupère l'ID d'interface d'un point de connexion.|  
|[CConnectionPoint::GetMaxConnections](../Topic/CConnectionPoint::GetMaxConnections.md)|Récupère le nombre maximal de points de connexion pris en charge par un contrôle.|  
|[CConnectionPoint::GetNextConnection](../Topic/CConnectionPoint::GetNextConnection.md)|Extrait un pointeur vers l'élément de connexion à `pos`.|  
|[CConnectionPoint::GetStartPosition](../Topic/CConnectionPoint::GetStartPosition.md)|Démarre une itération de mappage par retourner une valeur de **position** qui peut être passée à un appel d' `GetNextConnection` .|  
|[CConnectionPoint::OnAdvise](../Topic/CConnectionPoint::OnAdvise.md)|Appelé par l'infrastructure à l'établissement ou en désactivant des connexions.|  
|[CConnectionPoint::QuerySinkInterface](../Topic/CConnectionPoint::QuerySinkInterface.md)|Extrait un pointeur vers l'interface demandée de récepteur.|  
  
## Notes  
 Contrairement aux interfaces OLE normales, qui sont utilisées pour implémenter et exposer les fonctionnalités d'un contrôle OLE, implémente d'un point de connexion une interface sortante qui peut initialiser des actions sur d'autres objets, tels que les événements de mise à feu et des notifications de modifications.  
  
 Une connexion se compose de deux parties : l'objet appelant l'interface, l'appel de la source « , » et l'objet qui implémente l'interface, appelé « récepteur. » En exposant un point de connexion, une source permet aux récepteurs pour établir des connexions à elle\-même.  Via le mécanisme de point de connexion, un objet source obtient un pointeur vers l'implémentation du récepteur d'un ensemble de fonctions membres.  Par exemple, pour déclencher un événement implémenté par le destinataire, la source peut appeler la méthode appropriée de l'implémentation du récepteur.  
  
 Par défaut, `COleControl`\- la classe dérivée implémente deux points de connexion : un pour les événements et un pour les notifications de modifications de propriétés.  Ces connexions sont utilisées, respectivement, pour le déclenchement d'événements et pour avertir un destinataire \(par exemple, le conteneur du contrôle\) lorsqu'une valeur de propriété a été modifiée.  La prise en charge est également fourni pour les contrôles OLE pour implémenter les points de connexion supplémentaires.  Pour chaque point de connexion supplémentaires implémenté dans votre classe de contrôle, vous devez déclarer une « partie de connexion » cette instrumente le point de connexion.  Si vous implémentez un ou plusieurs points de connexion, vous devez également déclarer une « mappage de plug\-ins » unique dans votre classe de contrôle.  
  
 L'exemple suivant montre une carte de connexions simple et un point de connexion du contrôle OLE d' `Sample` , qui se compose de deux fragments de code : la première partie déclare le mappage de plug\-ins et le débogage ; le deuxième implémente ces mappages et point.  Le premier fragment est inséré dans la déclaration de la classe de contrôle, sous la section d' `protected` :  
  
 [!code-cpp[NVC_MFCConnectionPoints#7](../../mfc/codesnippet/CPP/cconnectionpoint-class_1.h)]  
  
 Les macros d' `BEGIN_CONNECTION_PART` et d' `END_CONNECTION_PART` déclarez une classe incorporée, `XSampleConnPt` \(dérivé d' `CConnectionPoint`\) qui implémente ce point de connexion spécifique.  Si vous souhaitez substituer les fonctions membres d' `CConnectionPoint` , ou ajouter des fonctions membres de vos propres, déclarez ceux\-ci entre ces deux macros.  Par exemple, la macro d' `CONNECTION_IID` substitue la fonction membre d' `CConnectionPoint::GetIID` une fois définie entre ces deux macros.  
  
 Le deuxième fragment de code est inséré dans le fichier d'implémentation \(.CPP\) de votre classe de contrôle.  Ce code implémente le mappage de connexions, qui inclut le point de connexion en outre, `SampleConnPt`:  
  
 [!code-cpp[NVC_MFCConnectionPoints#2](../../mfc/codesnippet/CPP/cconnectionpoint-class_2.cpp)]  
  
 Une fois ces fragments de code ont été insérés, le contrôle OLE exemple expose un point de connexion pour l'interface d' **ISampleSink** .  
  
 En général, les points de connexion prennent en charge la « multifusion », qui est la capacité de la diffuser à plusieurs récepteurs connectés à la même interface.  Le fragment de code suivant montre comment obtenir la multifusion en itérant au sein de chaque récepteur sur un point de connexion :  
  
 [!code-cpp[NVC_MFCConnectionPoints#4](../../mfc/codesnippet/CPP/cconnectionpoint-class_3.cpp)]  
  
 Cet exemple récupère l'ensemble actuel de connexions sur le point de connexion d' `SampleConnPt` avec un appel à `CConnectionPoint::GetConnections`.  Il itère au sein de les connexions et appelle `ISampleSink::SinkFunc` sur chaque connexion active.  
  
 Pour plus d'informations sur l'utilisation `CConnectionPoint`, consultez l'article [points de connexion](../../mfc/connection-points.md).  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 `CConnectionPoint`  
  
## Configuration requise  
 **Header:** afxdisp.h  
  
## Voir aussi  
 [CCmdTarget Class](../../mfc/reference/ccmdtarget-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)