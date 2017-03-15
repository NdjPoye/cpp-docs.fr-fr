---
title: "Calling C++ Code from DHTML | Microsoft Docs"
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
  - "DHTML, calling C++ code from"
ms.assetid: 37329acd-4c22-40ca-a85a-b7480748f75f
caps.latest.revision: 12
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Calling C++ Code from DHTML
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Un contrôle DHTML peut être hébergé dans un conteneur, tel que Test Container ou Internet Explorer.  Consultez [propriétés et événements de test avec Test Container](../mfc/testing-properties-and-events-with-test-container.md) pour plus d'informations sur l'accès à l'outil Test Container.  
  
 Le conteneur héberger le contrôle communique avec le contrôle à l'aide de les interfaces de contrôle normales.  DHTML utilise l'interface de dispatch qui se termine par « interface » pour communiquer avec votre code C\+\+ et votre ressource HTML.  Dans [Modifier le contrôle ATL DHTML](../atl/modifying-the-atl-dhtml-control.md), vous pouvez pratiquer ajouter des méthodes à appeler par ces différentes interfaces.  
  
 Pour obtenir un exemple d'appeler le code C\+\+ DHTML, de [créez un contrôle DHTML](../atl/creating-an-atl-dhtml-control.md) à l'aide de l'Assistant Contrôle ATL et examiner le code dans le fichier d'en\-tête et dans le fichier HTML.  
  
## Déclaration des méthodes WebBrowser dans le fichier d'en\-tête  
 Pour appeler des méthodes C\+\+ DHTML interface utilisateur, vous devez ajouter des méthodes à l'interface de l'interface utilisateur de votre contrôle.  Par exemple, le fichier d'en\-tête créé par l'Assistant Contrôle ATL contient la méthode `OnClick`C\+\+, qui est un membre de l'interface d'interface utilisateur du contrôle généré par l'Assistant.  
  
 Examinez `OnClick` dans le fichier du .h du contrôle :  
  
 [!code-cpp[NVC_ATL_COM#4](../atl/codesnippet/CPP/calling-cpp-code-from-dhtml_1.h)]  
  
 Le premier paramètre, `pdispBody`, est un pointeur vers l'interface de dispatch de l'objet de corps.  Le deuxième paramètre, `varColor`, identifie la couleur pour appliquer au contrôle.  
  
## Code C\+\+ appelant dans le fichier HTML  
 Une fois que vous avez déclaré les méthodes WebBrowser dans le fichier d'en\-tête, vous pouvez appeler les méthodes du fichier HTML.  Notez dans le fichier HTML que les insertions de l'Assistant Contrôle ATL trois fenêtres présentent des méthodes : trois méthodes d' `OnClick` qui présentent des des messages pour modifier la couleur d'arrière\-plan du contrôle.  
  
 Examinez l'une des méthodes dans le fichier HTML :  
  
 `<BUTTON onclick='window.external.OnClick(theBody, "red");'>Red</BUTTON>`  
  
 Dans le code HTML ci\-dessus, la méthode externe de la fenêtre, `OnClick`, est appelée dans le cadre de la balise de bouton.  La méthode possède deux paramètres : `theBody`, qui référence le corps du document HTML, et `"red"`, ce qui indique que la couleur d'arrière\-plan du contrôle sera modifiée en rouge lorsque l'utilisateur clique sur le bouton.  `Red` suivant l'indicateur est l'étiquette du bouton.  
  
 Consultez [Modifier le contrôle ATL DHTML](../atl/modifying-the-atl-dhtml-control.md) pour plus d'informations sur fournir vos propres méthodes.  Consultez l' [Identifier les éléments du projet de contrôle DHTML](../atl/identifying-the-elements-of-the-dhtml-control-project.md) pour plus d'informations sur le fichier HTML.  
  
## Voir aussi  
 [Prise en charge pour un contrôle DHTML](../atl/atl-support-for-dhtml-controls.md)