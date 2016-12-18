---
title: "Identifying the Elements of the DHTML Control Project | Microsoft Docs"
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
  - "DHTML controls, ATL support"
  - "contrôles HTML, ATL support"
ms.assetid: b627547a-3768-4346-9900-4b7a21fb8e27
caps.latest.revision: 11
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Identifying the Elements of the DHTML Control Project
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La plupart de code de contrôle DHTML est exactement comme que créé pour un contrôle ATL.  Pour une présentation de base de code générique, de travail via [Didacticiel ATL](../atl/active-template-library-atl-tutorial.md), et lu les sections [créer un projet ATL](../atl/reference/creating-an-atl-project.md) et [Notions de base des objets COM ATL](../atl/fundamentals-of-atl-com-objects.md).  
  
 Un contrôle DHTML est semblable à un contrôle ATL, sauf :  
  
-   Outre les interfaces regular un contrôle implémente, il implémente une interface supplémentaires qui est utilisée pour communiquer entre le code C\+\+ et l'interface utilisateur \(UI\) HTML.  Les appels du HTML interface utilisateur dans le code C\+\+ à l'aide de cette interface.  
  
-   Il crée une ressource HTML pour le contrôle interface utilisateur.  
  
-   Il permet l'accès au modèle objet DHTML via la variable membre `m_spBrowser`, qui est un pointeur intelligent de type [IWebBrowser2](https://msdn.microsoft.com/en-us/library/aa752127.aspx).  Utilisez ce pointeur pour accéder à une partie du modèle objet DHTML.  
  
 Le graphique suivant illustre la relation entre la DLL, le contrôle DHTML, le navigateur web, et la ressource HTML.  
  
 ![Éléments d'un projet de contrôle DHTML](../atl/media/vc52en1.png "vc52EN1")  
  
> [!NOTE]
>  Les noms sur le graphique sont des espaces réservés.  Les noms de votre ressource HTML et des interfaces exposées sur votre contrôle sont basés sur les noms que vous assignez \-les dans l'Assistant Contrôle ATL.  
  
 Dans ce graphique, les éléments sont :  
  
-   **My DLL** La DLL créé à l'aide de l'Assistant Projet ATL.  
  
-   **DHTML Control** \(\)`m_spBrowser`le contrôle DHTML, créé à l'aide de l'Assistant Objet ATL.  Ce contrôle accède à l'objet de navigateur web et à ses méthodes dans l'interface de l'objet de navigateur web, **IWebBrowser2**.  Le contrôle lui\-même expose les deux interfaces suivantes, en plus de les autres interfaces requises standard pour un contrôle.  
  
    -   **IDHCTL1** l'interface exposée par le contrôle pour être utilisé uniquement par le conteneur.  
  
    -   **IDHCTLUI1** l'interface de dispatch pour communiquer entre le code C\+\+ et l'interface utilisateur HTML.  Le navigateur web utilise l'interface de dispatch du contrôle pour afficher le contrôle.  Vous pouvez appeler des méthodes de cette interface de dispatch de l'interface utilisateur du contrôle en appelant `window.external`, suivi du nom de méthode sur cette interface de dispatch que vous souhaitez appeler.  Vous accéderiez à `window.external` d'une balise de SCRIPT dans le code HTML qui compose l'interface utilisateur pour ce contrôle.  Pour plus d'informations sur l'appel de méthodes externes dans le fichier de ressources, consultez [Code C\+\+ appelant DHTML](../atl/calling-cpp-code-from-dhtml.md).  
  
-   **IDR\_CTL1** l'ID de ressource de ressources HTML.  Son nom de fichier, dans ce cas, est DHCTL1UI.htm.  Le contrôle DHTML utilise une ressource HTML qui contient les balises HTML standard et l'expédition externe de la fenêtre commande que vous pouvez modifier à l'aide de l'éditeur de texte.  
  
-   **Web Browser** le navigateur web affiche l'interface utilisateur du contrôle, selon le HTML de la ressource HTML.  Pointeur vers l'interface d' **IWebBrowser2** du navigateur web est disponible dans le contrôle DHTML pour permettre l'accès au modèle objet DHTML.  
  
 L'Assistant Contrôle ATL génère un contrôle avec le code dans la ressource HTML et le fichier .cpp.  Vous pouvez compiler et exécuter le contrôle comme généré par l'assistant, puis affichez le contrôle dans le navigateur web ou d'ActiveX Control Test Container.  L'image ci\-dessous montre le contrôle ATL DHTML par défaut avec trois boutons affichés dans Test Container :  
  
 ![Contrôle ATL DHTML](../atl/media/vc52en2.png "vc52EN2")  
  
 Consultez [Créer un contrôle ATL DHTML](../atl/creating-an-atl-dhtml-control.md) pour commencer à créer un contrôle DHTML.  Consultez [propriétés et événements de test avec Test Container](../mfc/testing-properties-and-events-with-test-container.md) pour plus d'informations sur l'accès à l'outil Test Container.  
  
## Voir aussi  
 [Prise en charge pour un contrôle DHTML](../atl/atl-support-for-dhtml-controls.md)