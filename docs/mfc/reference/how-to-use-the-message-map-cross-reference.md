---
title: "Comment : utiliser le renvoi de la table des messages | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.mfc.messages
dev_langs: C++
helpviewer_keywords: windows [MFC], message maps
ms.assetid: 2e863d23-9e58-45ba-b5e4-a8ceefccd0c8
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: ffa7b39962d78476e971750e92569eb14229606b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="how-to-use-the-message-map-cross-reference"></a>Comment : utiliser la référence croisée de la table des messages
Dans les entrées d’étiqueté \<memberFxn >, écrire votre propre fonction membre dérivé [CWnd](../../mfc/reference/cwnd-class.md) classe. Donnez à votre fonction de n’importe quel nom de que votre choix. Autres fonctions, telles que `OnActivate`, sont des fonctions membres de classe `CWnd`. Si elle est appelée, elles passent le message à la `DefWindowProc` fonction Windows. Pour traiter les messages de notification Windows, remplacez correspondant `CWnd` fonction dans votre classe dérivée. Votre fonction doit appeler la fonction substituée dans votre classe de base pour vous permettre de la classe de base et Windows répondent au message.  
  
 Dans tous les cas, placez le prototype de fonction dans le `CWnd`-en-tête de classe dérivée et le code de l’entrée de mappage de message comme indiqué.  
  
 Les termes suivants sont utilisés :  
  
|Terme|Définition|  
|----------|----------------|  
|ID|Les utilisateurs définis par l’ID d’élément de menu (**WM_COMMAND** messages) ou ID (messages de notification de fenêtre enfant) du contrôle.|  
|« message » et « wNotifyCode »|ID de message Windows tel que défini dans WINDOWS. H.|  
|nMessageVariable|Nom d’une variable qui contient la valeur de retour à partir de la **RegisterWindowMessage** fonction Windows.|  
  
## <a name="see-also"></a>Voir aussi  
 [Tables des messages](../../mfc/reference/message-maps-mfc.md)

