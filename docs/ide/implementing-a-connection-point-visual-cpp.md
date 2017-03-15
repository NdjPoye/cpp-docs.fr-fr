---
title: "Impl&#233;mentation d&#39;un point de connexion (Visual C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "points de connexion (C++), implémenter"
  - "Implémentation d'un point de connexion (Assistant C++)"
ms.assetid: 5b37e4f9-73c9-4bef-b26d-365bc0662260
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Impl&#233;mentation d&#39;un point de connexion (Visual C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Pour implémenter un point de connexion à l'aide de l'Assistant Implémentation d'un point de connexion, vous devez avoir créé un projet en tant qu'application COM ATL ou qu'application MFC intégrant la prise en charge ATL.  Vous pouvez utiliser l'[Assistant Projet ATL](../atl/reference/atl-project-wizard.md) pour créer une application ATL, ou vous pouvez également [ajouter un objet ATL à votre application MFC](../mfc/reference/adding-atl-support-to-your-mfc-project.md) pour implémenter la prise en charge ATL pour une application MFC.  
  
> [!NOTE]
>  Pour plus d'informations sur l'implémentation des points de connexion pour un projet MFC, consultez [Points de connexion](../mfc/connection-points.md).  
  
 Lorsque vous créez un projet, pour implémenter un point de connexion, vous devez d'abord ajouter un objet ATL.  Pour obtenir la liste des Assistants permettant d'ajouter des objets à votre projet ATL, consultez [Ajout d'objets et de contrôles à un projet ATL](../atl/reference/adding-objects-and-controls-to-an-atl-project.md).  
  
> [!NOTE]
>  L'Assistant ne prend pas en charge les dialogues ATL, les services Web XML créés avec ATL Server, les objets de performance ou les compteurs de performance.  
  
 Un objet connectable \(c'est\-à\-dire une source\) peut exposer un point de connexion pour chacune de ses interfaces sortantes.  Chaque interface sortante peut être implémentée par un client sur un objet \(c'est\-à\-dire un récepteur\).  Pour plus d'informations, consultez [Points de connexion ATL](../atl/atl-connection-points.md).  
  
### Pour implémenter un point de connexion  
  
1.  Dans l'Affichage de classes, cliquez avec le bouton droit sur le nom de classe de votre objet ATL.  
  
2.  Dans le menu contextuel, cliquez sur **Ajouter**, puis sur **Ajouter un point de connexion** pour afficher l'[Assistant Implémentation d'un point de connexion](../ide/implement-connection-point-wizard.md).  
  
3.  Dans les bibliothèques de types appropriées, sélectionnez les interfaces de points de connexion à implémenter, puis cliquez sur **Terminer**.  
  
4.  Dans l'Affichage de classes, examinez les classes proxy créées pour chaque point de connexion.  Les classes s'affichent sous la forme CProxy*NomInterface*\<T\> et sont dérivées de [IConnectionPointImpl](../atl/reference/iconnectionpointimpl-class.md).  
  
5.  Double\-cliquez sur la classe du point de connexion afin d'afficher sa définition.  
  
    -   Si vous implémentez un point de connexion pour l'interface de votre projet personnel, la définition suivante s'affiche :  
  
        ```  
        template< class T >  
        class CProxyInterfaceName :  
           public IConnectionPointImpl< T, &IID_InterfaceName >  
        {  
        public:  
        };  
        ```  
  
         Si vous implémentez une interface locale, des méthodes et des propriétés s'affichent dans le corps de la classe.  
  
    -   Si vous implémentez un point de connexion pour une autre interface, la définition comprend les méthodes de l'interface, précédées chacune de `Fire_`.  
  
## Voir aussi  
 [Ajout de fonctionnalités à l'aide des Assistants Code](../ide/adding-functionality-with-code-wizards-cpp.md)   
 [Adding Connection Points to an Object](../atl/adding-connection-points-to-an-object.md)