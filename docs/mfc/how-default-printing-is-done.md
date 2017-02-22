---
title: "Impression par d&#233;faut | Microsoft Docs"
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
  - "impression par défaut"
  - "valeurs par défaut, imprimer"
  - "imprimer (MFC), par défaut"
ms.assetid: 0f698459-0fc9-4d43-97da-29cf0f65daa2
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Impression par d&#233;faut
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Cet article explique le processus d'impression par défaut dans windows en termes de infrastructure MFC.  
  
 Dans les applications de MFC, la classe d'affichage fournit une fonction membre `OnDraw` nommée qui contient le code de dessin.  prend`OnDraw` un pointeur vers un objet [CDC](../mfc/reference/cdc-class.md) comme paramètre.  Cet objet `CDC` représente le contexte de périphérique pour recevoir l'image générée par `OnDraw`.  Lorsque la fenêtre affichant le document reçoit un message [WM\_PAINT](http://msdn.microsoft.com/library/windows/desktop/dd145213), l'infrastructure appelle `OnDraw` et lui passe un contexte de périphérique pour l'écran \(objet [CPaintDC](../mfc/reference/cpaintdc-class.md), pour être précis\).  Par conséquent, la sortie de `OnDraw`passe à l'écran.  
  
 En programmation pour windows, envoyer la sortie vers l'imprimante est très similaire à envoyer la sortie à l'écran.  Cela est dû au fait que le Graphics Device Interface \(GDI\) Windows est indépendant du matériel.  Vous pouvez utiliser les mêmes fonctions de GDI pour afficher l'écran ou pour l'impression simplement à l'aide du contexte de périphérique.  Si l'objet `CDC` que `OnDraw` reçoit représente l'imprimante, la sortie de `OnDraw`va à l'imprimante.  
  
 Ceci explique comment les applications MFC peuvent effectuer une impression simple sans effort supplémentaire de votre part.  L'infrastructure prend soin d'afficher la boîte de dialogue Imprimer et de créer un contexte de périphérique pour l'imprimante.  Lorsque l'utilisateur sélectionne la commande imprimer du menu Fichier, la vue passe ce contexte de périphérique à `OnDraw`, qui dessine le document sur l'imprimante.  
  
 Toutefois, il existe des différences significatives entre l'impression et l'écran.  Lors de la copie, vous devez diviser le document en pages distinctes et les afficher une par une, plutôt que d'afficher n'importe quelle partie visible dans une fenêtre.  En corollaire, vous devez être informé que le format du papier \(qu'il s'agisse de taille de caractères, de format administratif, ou d'une forme\).  Vous pouvez imprimer dans différentes orientations, telles que le mode paysage et le mode portrait.  La bibliothèque MFC ne peut pas prévoir comment votre application traite ces problèmes, il fournit un protocole pour pouvoir ajouter ces fonctions.  
  
 Ce protocole est décrit dans l'article [Documents multipages](../mfc/multipage-documents.md).  
  
## Voir aussi  
 [Impression](../mfc/printing.md)