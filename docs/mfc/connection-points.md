---
title: Points de connexion | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- IConnectionPoint
dev_langs:
- C++
helpviewer_keywords:
- IConnectionPoint interface
- connections, connection points
- OLE COM connection points
- MFC COM, connection points
- COM, connection points
- interfaces, IConnectionPoint
- MFC, COM support
- connection points [MFC]
- CCmdTarget class [MFC], and connection points
- sinks, connection points
ms.assetid: bc9fd7c7-8df6-4752-ac8c-0b177442c88d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 56686fe4ea2920f9365b84ec3064df4be95f4a3b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="connection-points"></a>Points de connexion
Cet article explique comment implémenter des points de connexion (anciennement appelés points de connexion OLE) à l'aide des classes `CCmdTarget` et `CConnectionPoint` de MFC.  
  
 Dans le passé, le composant COM (Object Model) définissait un mécanisme général (**IUnknown::QueryInterface**) qui permettait aux objets d’implémenter et d’exposer des fonctionnalités dans les interfaces. Toutefois, un mécanisme de correspondance qui permettait aux objets de montrer leur capacité à appeler des interfaces spécifiques n'était pas défini. Autrement dit, le modèle COM définissait comment les pointeurs entrants aux objets (pointeurs aux interfaces de l'objet) étaient traités, mais il n'y avait pas de modèle explicite pour les interfaces sortantes (les pointeurs que l'objet conserve dans d'autres interfaces d'objets). COM a maintenant un modèle, appelé points de connexion, qui prend en charge cette fonctionnalité.  
  
 Une connexion est composée de deux parties : l'objet qui appelle l'interface, appelé la source, et l'objet implémentant l'interface, appelé le récepteur. Un point de connexion est l'interface exposée par la source. En exposant un point de connexion, une source permet à des récepteurs d'établir des connexions à elle-même (source). Via la connexion de point de mécanisme (le **IConnectionPoint** interface), un pointeur vers l’interface du récepteur est passé à l’objet source. Ce pointeur assure à la source l'accès à l'implémentation du récepteur d'un ensemble de fonctions membres. Par exemple, pour déclencher un événement implémenté par le récepteur, la source peut appeler la méthode appropriée de l'implémentation du récepteur. L'illustration suivante montre le point de connexion qui vient d'être décrit.  
  
 ![Implémenté le point de connexion](../mfc/media/vc37lh1.gif "vc37lh1")  
Un Point de connexion implémenté  
  
 MFC implémente ce modèle dans le [CConnectionPoint](../mfc/reference/cconnectionpoint-class.md) et [CCmdTarget](../mfc/reference/ccmdtarget-class.md) classes. Les classes dérivées de **CConnectionPoint** implémenter la **IConnectionPoint** interface utilisée pour exposer des points de connexion à d’autres objets. Les classes dérivées de `CCmdTarget` implémenter la **IConnectionPointContainer** interface, ce qui peut énumérer tous les points de connexion disponibles d’un objet ou trouver un point de connexion spécifique.  
  
 Pour chaque point de connexion implémenté dans votre classe, vous devez déclarer une partie de la connexion qui implémente le point de connexion. Si vous implémentez un ou plusieurs points de connexion, vous devez également déclarer un seul mappage de connexions dans votre classe. Un mappage de connexions est une table de points de connexion prise en charge par le contrôle ActiveX.  
  
 Les exemples suivants illustrent un mappage de connexions simple et un point de connexion. Le premier exemple déclare le mappage de connexions et le point ; le deuxième exemple implémente le mappage et le point. Notez que `CMyClass` doit être un `CCmdTarget`-classe dérivée. Dans le premier exemple, le code est inséré dans la déclaration de classe, sous la **protégé** section :  
  
 [!code-cpp[NVC_MFCConnectionPoints#1](../mfc/codesnippet/cpp/connection-points_1.h)]  
  
 Le `BEGIN_CONNECTION_PART` et **END_CONNECTION_PART** macros déclarent une classe incorporée, `XSampleConnPt` (dérivée de `CConnectionPoint`), que le point de cette connexion particulier implémente. Si vous souhaitez remplacer toutes les fonctions membres de `CConnectionPoint` ou ajouter vos propres fonctions membres, déclarez-les entre ces deux macros. Par exemple, la macro `CONNECTION_IID` remplace la fonction membre `CConnectionPoint::GetIID` lorsqu'elle est placée entre ces deux macros.  
  
 Dans le deuxième exemple, le code est inséré dans le fichier d'implémentation du contrôle (fichier .cpp). Ce code implémente le mappage de connexions, notamment le point de connexion, `SampleConnPt` :  
  
 [!code-cpp[NVC_MFCConnectionPoints#2](../mfc/codesnippet/cpp/connection-points_2.cpp)]  
  
 Si la classe a plusieurs points de connexion, insérez des macros `CONNECTION_PART` supplémentaires entre les macros `BEGIN_CONNECTION_MAP` et `END_CONNECTION_MAP`.  
  
 Enfin, ajoutez un appel à la méthode `EnableConnections` dans le constructeur de la classe. Par exemple :  
  
 [!code-cpp[NVC_MFCConnectionPoints#3](../mfc/codesnippet/cpp/connection-points_3.cpp)]  
  
 Une fois ce code a été inséré, votre `CCmdTarget`-classe dérivée expose un point de connexion pour le **ISampleSink** interface. La figure suivante illustre cet exemple:  
  
 ![Point de connexion implémenté à l’aide de MFC](../mfc/media/vc37lh2.gif "vc37lh2")  
Un point de connexion implémenté avec MFC  
  
 Généralement, les points de connexion prennent en charge la "multidiffusion" : la capacité de distribution à plusieurs récepteurs connectés à la même interface. Le fragment de l'exemple suivant montre comment utiliser la multidiffusion en parcourant chaque destinataire sur un point de connexion :  
  
 [!code-cpp[NVC_MFCConnectionPoints#4](../mfc/codesnippet/cpp/connection-points_4.cpp)]  
  
 Cet exemple récupère l'ensemble actuel de connexions sur le point de connexion `SampleConnPt` par un appel à `CConnectionPoint::GetConnections`. Il itère ensuite les connexions et appelle **ISampleSink::SinkFunc** sur chaque connexion active.  
  
## <a name="see-also"></a>Voir aussi  
 [MFC COM](../mfc/mfc-com.md)

