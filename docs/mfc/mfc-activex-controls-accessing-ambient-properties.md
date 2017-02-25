---
title: "Contr&#244;les ActiveX MFC&#160;: acc&#232;s aux propri&#233;t&#233;s ambiantes | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "contrôles ActiveX MFC, accéder aux propriétés ambiantes"
  - "propriétés (MFC), accéder (ambiantes)"
ms.assetid: fdc9db29-e6b0-45d2-a879-8bd60e2058a7
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Contr&#244;les ActiveX MFC&#160;: acc&#232;s aux propri&#233;t&#233;s ambiantes
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Cet article explique comment un contrôle ActiveX peut accéder aux propriétés ambiantes de son conteneur de contrôle.  
  
 Un contrôle peut obtenir des informations sur son conteneur lors de l'accès aux propriétés ambiantes du conteneur.  Ces propriétés présentent des caractéristiques visuelles, telles que la couleur d'arrière\-plan du conteneur, la police actuelle utilisée par le conteneur, et les fonctionnalités opérationnelles, par exemple si le conteneur est actuellement en mode utilisateur ou en mode du concepteur.  Un contrôle peut utiliser les propriétés ambiantes pour concevoir son apparence et le comportement du conteneur particulier dans lequel il est incorporé.  Toutefois, un contrôle ne doit jamais supposer que son conteneur prend en charge une propriété ambiante particulière.  En fait, certains conteneurs peuvent ne pas prendre en charge les propriétés ambiantes du tout.  En l'absence de propriété ambiante, un contrôle doit supposer une valeur par défaut raisonnable.  
  
 Pour accéder à une propriété ambiante, effectuez un appel à [COleControl::GetAmbientProperty](../Topic/COleControl::GetAmbientProperty.md).  Cette fonction s'attend à ce que l'ID de dispatch de la propriété ambiante soit le premier paramètre \(le fichier OLECTL.H définit les ID de transaction pour un ensemble standard de propriétés ambiantes\).  
  
 Les paramètres de la fonction `GetAmbientProperty` sont l'ID de dispatch, une balise variante indiquant le type de propriété attendue, et un pointeur vers la mémoire dans laquelle la valeur doit être retournée.  Le type de données auquel ce pointeur fait référence varie selon la balise variante.  La fonction retourne **TRUE** si le conteneur prend en charge la propriété, sinon il renvoie **FALSE**.  
  
 L'exemple de code suivant obtient la valeur de la propriété ambiante appelée « UserMode ». Si la propriété n'est pas prise en charge par le conteneur, une valeur par défaut **TRUE** est utilisée :  
  
 [!code-cpp[NVC_MFC_AxUI#30](../mfc/codesnippet/CPP/mfc-activex-controls-accessing-ambient-properties_1.cpp)]  
  
 Pour plus de commodité, `COleControl` fournit les fonctions d'assistance qui accèdent à plusieurs des propriétés ambiantes couramment utilisées et retourne les valeurs par défaut appropriées lorsque les propriétés sont pas disponibles.  Ces fonctions d'assistance sont les suivantes :  
  
-   [COleControl::AmbientBackColor](../Topic/COleControl::AmbientBackColor.md)  
  
-   [AmbientDisplayName](../Topic/COleControl::AmbientDisplayName.md)  
  
-   [AmbientFont](../Topic/COleControl::AmbientFont.md)  
  
    > [!NOTE]
    >  L'appelant doit appeler **Release\( \)** sur la police retournée.  
  
-   [AmbientForeColor](../Topic/COleControl::AmbientForeColor.md)  
  
-   [AmbientLocaleID](../Topic/COleControl::AmbientLocaleID.md)  
  
-   [AmbientScaleUnits](../Topic/COleControl::AmbientScaleUnits.md)  
  
-   [AmbientTextAlign](../Topic/COleControl::AmbientTextAlign.md)  
  
-   [AmbientUserMode](../Topic/COleControl::AmbientUserMode.md)  
  
-   [AmbientUIDead](../Topic/COleControl::AmbientUIDead.md)  
  
-   [AmbientShowHatching](../Topic/COleControl::AmbientShowHatching.md)  
  
-   [AmbientShowGrabHandles](../Topic/COleControl::AmbientShowGrabHandles.md)  
  
 Si la valeur d'une propriété ambiante change \(via une action du conteneur\), la fonction membre **OnAmbientPropertyChanged** du contrôle est appelée.  Remplacez cette fonction membre pour traiter une telle notification.  Le paramètre pour **OnAmbientPropertyChanged** est l'ID de dispatch de la propriété ambiante affectée.  La valeur de l'ID de dispatch peut être **DISPID\_UNKNOWN**, ce qui signifie qu'une ou plusieurs propriétés ambiantes ont changé, mais les informations sur les propriétés affectées ne sont pas disponibles.  
  
## Voir aussi  
 [Contrôles ActiveX MFC](../mfc/mfc-activex-controls.md)