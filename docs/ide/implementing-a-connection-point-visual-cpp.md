---
title: "Implémentation d’un Point de connexion (Visual C++) | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- Implement Connection Point Wizard [C++]
- connection points [C++], implementing
ms.assetid: 5b37e4f9-73c9-4bef-b26d-365bc0662260
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ab065c78d8ea5d2de105abdc2fa651e05f9d1875
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="implementing-a-connection-point-visual-c"></a>Implémentation d'un point de connexion (Visual C++)
Pour implémenter un point de connexion à l’aide de l’Assistant implémenter de Point de connexion, vous devez avoir créé un projet comme une application ATL COM ou comme une application MFC qui contient la prise en charge ATL. Vous pouvez utiliser la [Assistant Projet ATL](../atl/reference/atl-project-wizard.md) pour créer une application ATL, ou [ajouter un objet ATL à votre application MFC](../mfc/reference/adding-atl-support-to-your-mfc-project.md) pour implémenter la prise en charge ATL pour une application MFC.  
  
> [!NOTE]
>  Pour plus d’informations sur l’implémentation des points de connexion pour un projet MFC, consultez [Points de connexion](../mfc/connection-points.md).  
  
 Une fois que vous créez un projet, pour implémenter un point de connexion, vous devez d’abord ajouter un objet ATL. Consultez [Ajout d’objets et des contrôles à un projet ATL](../atl/reference/adding-objects-and-controls-to-an-atl-project.md) pour obtenir la liste des Assistants permettant d’ajouter des objets à votre projet ATL.  
  
> [!NOTE]
>  L’Assistant ne prend pas en charge les dialogues ATL, les services Web XML créés avec ATL Server, les objets de performance ou les compteurs de performance.  
  
 Un objet connectable (c'est-à-dire une source) peut exposer un point de connexion pour chacune de ses interfaces sortantes. Chaque interface sortante peut être implémentée par un client sur un objet (autrement dit, un récepteur). Pour plus d’informations, consultez [Points de connexion ATL](../atl/atl-connection-points.md).  
  
### <a name="to-implement-a-connection-point"></a>Pour implémenter un point de connexion  
  
1.  Dans Affichage de classes, cliquez sur le nom de classe pour votre objet ATL.  
  
2.  Cliquez sur **ajouter** dans le menu contextuel, puis cliquez sur **ajouter un Point de connexion** pour afficher les [l’Assistant Implémentation d’un Point de connexion](../ide/implement-connection-point-wizard.md).  
  
3.  Sélectionnez les interfaces de point de connexion à implémenter dans les bibliothèques de type approprié, puis cliquez sur **Terminer**.  
  
4.  Dans l’affichage de classes, examinez les classes proxy créés pour chaque point de connexion. Les classes s’affichent sous la forme CProxy*InterfaceName*\<T > et sont dérivés de [IConnectionPointImpl](../atl/reference/iconnectionpointimpl-class.md).  
  
5.  Double-cliquez sur la classe de point de connexion pour afficher la définition de classe du point de connexion.  
  
    -   Si vous implémentez un point de connexion pour l’interface de votre propre projet, la définition suivante s’affiche  
  
        ```  
        template< class T >  
        class CProxyInterfaceName :  
           public IConnectionPointImpl< T, &IID_InterfaceName >  
        {  
        public:  
        };  
        ```  
  
         Si vous implémentez une interface locale, les méthodes et propriétés apparaissent dans le corps de la classe.  
  
    -   Si vous implémentez un point de connexion pour une autre interface, la définition comprend les méthodes de l’interface, précédées chacune `Fire_`.  
  
## <a name="see-also"></a>Voir aussi  
 [Ajout de fonctionnalités à l’aide des Assistants Code](../ide/adding-functionality-with-code-wizards-cpp.md)   
 [Ajout de points de connexion à un objet](../atl/adding-connection-points-to-an-object.md)