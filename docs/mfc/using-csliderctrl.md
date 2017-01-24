---
title: "Utilisation de CSliderCtrl | Microsoft Docs"
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
  - "CSliderCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSliderCtrl (classe), utilisation"
  - "contrôles Slider, utilisation"
ms.assetid: 242c7bcd-126e-4b9b-8f76-8082ad06fe73
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Utilisation de CSliderCtrl
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La classe d' [CSliderCtrl](../mfc/reference/csliderctrl-class.md) représente un contrôle de curseur, également appelé trackbar.  Un « contrôle de curseur » est une fenêtre qui contient un curseur et des graduations facultatives.  Lorsque l'utilisateur déplace le curseur, à l'aide de la souris ou des touches de direction, le contôle du curseur envoie des messages de notification pour indiquer la modification.  
  
 Les contrôles de curseur sont utiles lorsque vous souhaitez que l'utilisateur sélectionne une valeur discrète ou un ensemble de valeurs consécutives dans une gamme.  Par exemple, vous pouvez utiliser un contôle de curseur pour permettre à l'utilisateur de définir la fréquence de répétition du clavier en déplaçant le curseur à une graduation donnée.  
  
 Le curseur dans un contôle de curseur se déplace par incrémentations que vous spécifiez lorsque vous le créez.  Par exemple, si vous spécifiez que le contôle de curseur doit avoir une plage de cinq, le curseur ne peut occuper que six positions : une position à gauche du contrôle de curseur et une position pour chaque incrément de la plage.  En général, chacune de ces positions est identifiée par une graduation.  
  
## Sur quels éléments souhaitez\-vous obtenir des informations supplémentaires ?  
  
-   [Utilisation de Contrôles de Curseur](../mfc/using-slider-controls.md)  
  
-   [Styles de Contrôles de Curseur](../mfc/slider-control-styles.md)  
  
-   [Fonctions Membres de Contrôles de Curseur](../mfc/slider-control-member-functions.md)  
  
-   [Messages de notification du Curseur](../mfc/slider-notification-messages.md)  
  
## Voir aussi  
 [Contrôles](../mfc/controls-mfc.md)