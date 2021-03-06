---
title: ATL et le marshaleur libre | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- ATL, free threaded marshaler
- free threaded marshaler
- threading [C++], marshaler in ATL
- threading [ATL], free threaded marshaler
- FTM in ATL
ms.assetid: 2db88a13-2217-4ebc-aa7e-432d5da902eb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1716985adf65b714a418f20d3873f45c32d368b4
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="atl-and-the-free-threaded-marshaler"></a>ATL et le marshaleur libre de threads
Page de l’Assistant objet Simple ATL attributs fournit une option qui permet à votre classe d’agréger FTM (FTM).  
  
 L’Assistant génère le code pour créer une instance de FTM dans `FinalConstruct` et libère cette instance dans `FinalRelease`. A `COM_INTERFACE_ENTRY_AGGREGATE` macro est automatiquement ajouté au mappage COM pour vous assurer que `QueryInterface` pour les demandes [IMarshal](http://msdn.microsoft.com/library/windows/desktop/dd542707) sont gérés par le marshaleur libre.  
  
 Le marshaleur libre de permet d’accéder directement aux interfaces sur votre objet à partir de n’importe quel thread dans le même processus, ce qui accélère les appels d’intercloisonnements. Cette option est destinée aux classes qui utilisent le modèle de thread à la fois.  
  
 Lorsque vous utilisez cette option, les classes doivent être responsable de la sécurité des threads de leurs données. En outre, les objets qui agrègent FTM et qui doivent utiliser des pointeurs d’interface obtenus à partir d’autres objets doivent suivre des étapes supplémentaires pour garantir que les interfaces sont correctement marshalés. En général, cela implique de stocker les pointeurs d’interface dans le tableau global d’interface (GIT) et l’obtention du pointeur de la GIT chaque fois qu’il est utilisé. ATL fournit la classe [CComGITPtr](../atl/reference/ccomgitptr-class.md) pour vous aider à utiliser des pointeurs d’interface stockés dans le GIT.  
  
## <a name="see-also"></a>Voir aussi  
 [Concepts](../atl/active-template-library-atl-concepts.md)   
 [CoCreateFreeThreadedMarshaler](http://msdn.microsoft.com/library/windows/desktop/ms694500)   
 [IMarshal](http://msdn.microsoft.com/library/windows/desktop/dd542707)   
 [Quand utiliser le tableau Global d’Interface](http://msdn.microsoft.com/library/windows/desktop/ms693729)   
 [Problèmes liés aux threads de serveur in-Process](http://msdn.microsoft.com/library/windows/desktop/ms687205)

