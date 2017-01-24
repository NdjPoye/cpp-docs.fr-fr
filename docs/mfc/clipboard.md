---
title: "Presse-papiers | Microsoft Docs"
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
  - "Presse-papiers"
  - "Presse-papiers, programmation"
  - "copier les données"
  - "couper et copier des données"
  - "transférer des données"
ms.assetid: a71b2824-1f14-4914-8816-54578d73ad4e
caps.latest.revision: 10
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Presse-papiers
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Cette famille d'articles explique comment implémenter la prise en charge du presse\-papiers Windows dans des applications MFC.  Le presse\-papiers windows est utilisé de plusieurs façons :  
  
-   En implémentant les commandes de menu Edition standard, telles que couper, copier et coller.  
  
-   Implémenter le transfert de données uniforme avec un glisser\/déposer \(OLE\).  
  
 Le presse\-papiers est la méthode standard Windows de transfert des données entre une source et une destination.  Il peut également s'avérer très utile dans les opérations OLE.  Avec l'arrivée OLE, il existe deux mécanismes de presse\-papiers dans Windows.  L'API standard du presse\-papiers Windows est toujours disponible, mais elle a été effectuée avec le mécanisme de transfert de données OLE.  Le transfert de données uniforme \(UDT\) OLE prend en charge le couper, copier etcoller dans le presse\-papiers ainsi que le glisser déposer.  
  
 Le presse\-papiers est un service système partagé par la session entière Windows, donc il n'a pas de descripteur ou une classe unique.  Vous gérez le presse\-papiers par le biais de fonctions membres de la classe [CWnd](../mfc/reference/cwnd-class.md).  
  
## Sur quels éléments souhaitez\-vous obtenir des informations supplémentaires ?  
  
-   [Quand utiliser chaque mécanisme du Presse\-papiers](../mfc/clipboard-when-to-use-each-clipboard-mechanism.md)  
  
-   [Utilisation de l'API traditionnelle du presse\-papiers Windows](../mfc/clipboard-using-the-windows-clipboard.md)  
  
-   [À l'aide du mécanisme OLE du presse\-papiers](../mfc/clipboard-using-the-ole-clipboard-mechanism.md)  
  
-   [Copier et coller des données](../mfc/clipboard-copying-and-pasting-data.md)  
  
-   [Ajouter d'autres formats](../mfc/clipboard-adding-other-formats.md)  
  
-   [\<caps:sentence id\="tgt18" sentenceid\="1bc8aafd7da110d0b343b54cffa169d9" class\="tgtSentence"\>Le presse\-papiers Windows\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/ms648709)  
  
-   [Implémentation du glisser\-déposer \(OLE\)](../mfc/drag-and-drop-ole.md)  
  
## Voir aussi  
 [Éléments de l'interface utilisateur](../mfc/user-interface-elements-mfc.md)