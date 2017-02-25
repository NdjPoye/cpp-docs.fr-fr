---
title: "Presse-papiers&#160;: utilisation du m&#233;canisme de Presse-papiers OLE | Microsoft Docs"
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
  - "applications (OLE), Presse-papiers"
  - "Presse-papiers (C++), formats d'OLE"
  - "formats (C++), Presse-papiers pour OLE"
  - "OLE (Presse-papiers)"
  - "OLE (Presse-papiers), formats"
ms.assetid: 229cc610-5bb1-435e-bd20-2c8b9964d1af
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Presse-papiers&#160;: utilisation du m&#233;canisme de Presse-papiers OLE
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

OLE utilise des formats standard et certains formats spécifiques à OLE pour transférer des données à travers le presse\-papiers.  
  
 Lorsque vous découpez ou copiez des données à partir d'une application, les données sont stockées dans le presse\-papiers pour être utilisées ultérieurement dans les opérations de collage.  Ces données sont dans divers formats.  Lorsqu'un utilisateur choisit de coller des données à partir de le presse\-papiers, l'application qui peut choisir lequel de ces formats utiliser.  L'application doit être écrite pour choisir le format qui offre le plus d'informations, à moins que l'utilisateur demande spécifiquement un certain format, utilisant un collage spécial.  Avant de continuer, vous pouvez lire les rubriques [Objets de données et sources de données \(OLE\)](../mfc/data-objects-and-data-sources-ole.md).  Elles décrivent les aspects fondamentaux de la façon dont les transferts de données fonctionnent, et leur implémentation dans vos applications.  
  
 Windows définit plusieurs formats standard qui peuvent être utilisés pour transférer des données dans le presse\-papiers.  Cela inclut les métafichiers, le texte, les images bitmap, entre autres.  OLE définit plusieurs formats spécifiques OLE.  Pour les applications qui nécessitent plus de détail que spécifié par ces formats standard, il est judicieux d'enregistrer leurs propres formats personnalisés de presse\-papiers.  Utilisez la fonction [RegisterClipboardFormat](http://msdn.microsoft.com/library/windows/desktop/ms649049) de l'API Win32 pour cela.  
  
 Par exemple, Microsoft Excel enregistre un format personnalisé pour les feuilles de calcul.  Ce format contient davantage d'informations qu'une bitmap par exemple.  Lorsque ces données sont collées dans une application qui prend en charge le format feuille de calcul, toutes les formules et valeurs de la feuille de calcul sont conservées et peuvent être mises à jour si nécessaire.  Microsoft Excel met également des données formatées dans le presse\-papiers afin qu'elles puissent être collées comme des éléments OLE.  Tout conteneur de document OLE peut également coller ces informations comme élément incorporé.  Cet élément incorporé peut être modifié à l'aide de Microsoft Excel.  Le presse\-papiers contient également une bitmap simple de l'image de la plage sélectionnée dans la feuille de calcul.  Ceci peut aussi être collé dans des conteneurs de document OLE ou dans des éditeurs de bitmaps, comme Paint.  Dans le cas d'une bitmap, toutefois, il n'existe aucune méthode pour manipuler les données sous la forme d'une feuille de calcul.  
  
 Pour récupérer le maximum d'informations du presse\-papiers, les applications doivent vérifier ces formats personnalisés avant de copier les données du presse\-papiers.  
  
 Par exemple, pour activer la commande de secteur, vous pouvez entrer à un gestionnaire quelque chose similaire à ce qui suit :  
  
 [!code-cpp[NVC_MFCListView#3](../mfc/codesnippet/CPP/clipboard-using-the-ole-clipboard-mechanism_1.cpp)]  
  
## Sur quels éléments souhaitez\-vous obtenir des informations supplémentaires ?  
  
-   [copie et collage de données](../mfc/clipboard-copying-and-pasting-data.md)  
  
-   [Ajouter d'autres formats](../mfc/clipboard-adding-other-formats.md)  
  
-   [Utilisation du presse\-papiers windows](../mfc/clipboard-using-the-windows-clipboard.md)  
  
-   [OLE](../mfc/ole-background.md)  
  
-   [Objets OLE de données et sources de données et transfert de données uniforme](../mfc/data-objects-and-data-sources-ole.md)  
  
## Voir aussi  
 [Presse\-papiers](../mfc/clipboard.md)