---
title: "Points de connexion | Microsoft Docs"
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
  - "IConnectionPoint"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CCmdTarget (classe), et points de connexion"
  - "COM, points de connexion"
  - "points de connexion (C++)"
  - "connexions, points de connexion"
  - "IConnectionPoint (interface)"
  - "interfaces, IConnectionPoint"
  - "MFC (C++), prise en charge COM"
  - "MFC COM, points de connexion"
  - "points de connexion OLE COM"
  - "récepteurs, points de connexion"
ms.assetid: bc9fd7c7-8df6-4752-ac8c-0b177442c88d
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Points de connexion
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Cet article explique comment implémenter des points de connexion \(anciennement appelé points de connexion OLE\) à l'aide des classes `CCmdTarget` et `CConnectionPoint`de MFC.  
  
 Dans le passé, le modèle COM \(component object model\) définissait un mécanisme général \(**IUnknown::QueryInterface**\) qui autorisait aux objets d'implémenter et de tirer parti des fonctionnalités dans les interfaces.  Toutefois, un mécanisme de correspondance qui permettait aux objets de montrer leur capacité à appeler des interfaces spécifiques n'a pas été défini.  Autrement dit, COM définissait comment les pointeurs entrants aux objets \(pointeurs aux interfaces de l'objet\) ont été traités, mais il n'a pas eu un modèle explicite pour les interfaces sortantes \(les pointeurs que l'objet tient vers d'autres interfaces d'objets\).  COM a maintenant un modèle, appelé points de connexion, qui prend en charge cette fonctionnalité.  
  
 Une connexion est composée de deux parties : l'objet qui appelle l'interface, appelé la source, et l'objet implémentant l'interface, appelé le récepteur.  Un point de connexion est l'interface exposée par la source.  En exposant un point de connexion, une source permet à des récepteurs d'établir des connexions à elle\-même \(source\).  A travers le mécanisme de point de connexion \(l'interface **IConnectionPoint** \), un pointeur vers l'interface du récepteur est transmis à l'objet source.  Ce pointeur assure à la source l'accès à l'implémentation du récepteur d'un ensemble de fonctions membres.  Par exemple, pour déclencher un événement implémenté par le récepteur, la source peut appeler la méthode appropriée de l'implémentation du récepteur.  L'illustration suivante montre le point de connexion qui vient d'être décrit.  
  
 ![Point de connexion implémenté](../mfc/media/vc37lh1.png "vc37LH1")  
Un Point de connexion implémenté  
  
 MFC implémente ce modèle dans les classes [CConnectionPoint](../mfc/reference/cconnectionpoint-class.md) et [CCmdTarget](../mfc/reference/ccmdtarget-class.md).  Les classes dérivées de **CConnectionPoint** implémentent l'interface de **IConnectionPoint**, utilisée pour exposer des points de connexion à d'autres objets.  Les classes dérivées de `CCmdTarget` implémentent l'interface de **IConnectionPointContainer**, qui peut énumérer tous les points de connexions disponibles d'un objet ou trouver un point de connexion spécifique.  
  
 Pour chaque point de connexion implémenté dans votre classe, vous devez déclarer une partie de la connexion qui implémente le délai de connexion.  Si vous implémentez un ou plusieurs points de connexion, vous devez également déclarer une seule mappage de connexions dans votre classe.  Une mappage de connexions est une table de connexion prise en charge par le contrôle ActiveX.  
  
 Les exemples suivants illustrent une mappage simple de connexions et un délai de connexion.  Le premier exemple déclare le mappage de connexions et le point ; le deuxième exemple implémente le mappage et le point.  Notez que `CMyClass` doit être une classe dérivée de `CCmdTarget` Dans le premier exemple, le code est inséré dans la déclaration de classe, sous la section **protégée** :  
  
 [!code-cpp[NVC_MFCConnectionPoints#1](../mfc/codesnippet/CPP/connection-points_1.h)]  
  
 Les macros `BEGIN_CONNECTION_PART` et **END\_CONNECTION\_PART** déclarent une classe incorporée, `XSampleConnPt` \(dérivée de `CConnectionPoint`\), qui met en œuvre ce point de connexion particulier.  Si vous souhaitez remplacer toutes les fonctions membres de `CConnectionPoint` ou ajouter vos propres fonctions membres, déclarez\-les entre ces deux macros.  Par exemple, la macro `CONNECTION_IID` remplace la fonction membre `CConnectionPoint::GetIID` lorsqu'elle est placée entre ces deux macros.  
  
 Dans le deuxième exemple, le code est inséré dans le fichier d'implémentation du contrôle \(fichier .cpp\).  Ce code implémente le mappage de connexions, notamment le point de connexion, `SampleConnPt`:  
  
 [!code-cpp[NVC_MFCConnectionPoints#2](../mfc/codesnippet/CPP/connection-points_2.cpp)]  
  
 Si la classe a plusieurs points de connexion, insérez des macros `CONNECTION_PART` supplémentaires entre les macros `BEGIN_CONNECTION_MAP` et `END_CONNECTION_MAP`.  
  
 Enfin, Ajoutez un appel à la méthode `EnableConnections` dans le constructeur de classe.  Par exemple :  
  
 [!code-cpp[NVC_MFCConnectionPoints#3](../mfc/codesnippet/CPP/connection-points_3.cpp)]  
  
 Une fois ce code inséré, votre classe dérivée de `CCmdTarget` expose un point de connexion pour l'interface de **ISampleSink** .  La figure suivante illustre cet exemple:  
  
 ![Point de connexion implémenté avec MFC](../mfc/media/vc37lh2.png "vc37LH2")  
Un Point de connexion implémenté avec MFC  
  
 Généralement, les points de connexions prennent en charge la "multifusion" — la capacité de distribuer à plusieurs récepteurs connectés à la même interface.  Le fragment de l'exemple suivant montre comment utiliser la multidiffusion en parcourant chaque destinataire sur un point de connexion :  
  
 [!code-cpp[NVC_MFCConnectionPoints#4](../mfc/codesnippet/CPP/connection-points_4.cpp)]  
  
 Cet exemple récupère l'ensemble actuel de connexions sur le point de connexion `SampleConnPt` par un appel à `CConnectionPoint::GetConnections`.  Il parcourt ensuite les connexions et appelle **ISampleSink::SinkFunc** sur chaque connexion active.  
  
## Voir aussi  
 [MFC COM](../mfc/mfc-com.md)