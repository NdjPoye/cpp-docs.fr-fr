---
title: "Ajout d&#39;une nouvelle interface &#224; un projet ATL | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "vc.appwiz.ATL.interface"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "projets ATL, ajouter des interfaces"
  - "controls [ATL], interfaces"
  - "Implémentation d'interface ATL (Assistant)"
  - "interfaces, ajouter aux objets ATL"
ms.assetid: 7d34b023-2c6b-4155-aca3-d47a40968063
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# Ajout d&#39;une nouvelle interface &#224; un projet ATL
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Lorsque vous ajoutez une interface à votre objet ou contrôle, vous créez des fonctions stubbed\-out pour chaque méthode contenue dans cette interface.  Seules des interfaces figurant dans une bibliothèque de types existante peuvent être ajoutées à votre objet ou contrôle.  De plus, la classe à laquelle est ajoutée l'interface doit implémenter la macro [BEGIN\_COM\_MAP](../Topic/BEGIN_COM_MAP.md) ou, si le projet utilise des attributs, il doit posséder l'attribut `coclass`.  
  
 Il existe deux méthodes pour ajouter une nouvelle interface à votre contrôle : manuellement ou à l'aide des Assistants Code de la fenêtre Affichage de classes.  
  
### Pour ajouter une interface à un objet ou contrôle existant à l'aide des Assistants Code de la fenêtre Affichage de classes  
  
1.  Dans l'[affichage de classes](http://msdn.microsoft.com/fr-fr/8d7430a9-3e33-454c-a9e1-a85e3d2db925), cliquez avec le bouton droit sur le nom de classe d'un contrôle.  Par exemple, choisissez un contrôle complet ou un contrôle composite, ou toute autre classe de contrôle qui implémente une macro BEGIN\_COM\_MAP dans son fichier d'en\-tête.  
  
2.  Dans le menu contextuel, cliquez sur **Ajouter**, puis sur **Implémenter l'interface**.  
  
3.  Sélectionnez les interfaces à implémenter dans l'[Assistant Implémentation d'interface](../../ide/implement-interface-wizard.md).  Si une interface sélectionnée n'existe dans aucune des typelibs disponibles, vous devez l'ajouter manuellement dans le fichier .idl.  
  
### Pour ajouter manuellement une nouvelle interface  
  
1.  Ajoutez la définition de la nouvelle interface dans le fichier .idl.  
  
2.  Dérivez votre objet ou contrôle de l'interface.  
  
3.  Créez une nouvelle entrée [COM\_INTERFACE\_ENTRY](../Topic/COM_INTERFACE_ENTRY%20\(ATL\).md) pour l'interface ou, si le projet utilise des attributs, ajoutez l'attribut `coclass`.  
  
4.  Implémentez les méthodes de l'interface.  
  
## Voir aussi  
 [Assistant Projet ATL](../../atl/reference/atl-project-wizard.md)   
 [Types de projets Visual C\+\+](../../ide/visual-cpp-project-types.md)   
 [Création de projets de bureau à l'aide des Assistants Application](../../ide/creating-desktop-projects-by-using-application-wizards.md)   
 [Programmation avec ATL et le code C Run\-Time](../../atl/programming-with-atl-and-c-run-time-code.md)   
 [Fundamentals of ATL COM Objects](../../atl/fundamentals-of-atl-com-objects.md)   
 [Configurations des projets ATL par défaut](../../atl/reference/default-atl-project-configurations.md)