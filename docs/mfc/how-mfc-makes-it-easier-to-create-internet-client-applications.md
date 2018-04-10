---
title: Comment MFC facilite la création d’Applications de Client Internet | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-windows
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- Internet client applications [MFC], MFC
- Internet applications [MFC], MFC
- MFC, Internet applications
ms.assetid: 94437b3f-f15c-437d-b5fd-264a2efec9ab
caps.latest.revision: 9
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f6270cdd3e64d24f1c2000acb9e8466f8c85edba
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="how-mfc-makes-it-easier-to-create-internet-client-applications"></a>Comment MFC facilite la création d'applications clientes Internet
Microsoft Foundation Classes encapsulent les fonctions d’Extension Internet Win32 (WinInet) d’une manière qui fournit un contexte familier aux programmeurs MFC. MFC fournit trois classes de fichiers Internet ([CInternetFile](../mfc/reference/cinternetfile-class.md), [CHttpFile](../mfc/reference/chttpfile-class.md), et [CGopherFile](../mfc/reference/cgopherfile-class.md)) dérivées de la [CStdioFile](../mfc/reference/cstdiofile-class.md) classe . Non seulement ces classes effectuez la récupération et la manipulation de données Internet familier aux programmeurs qui ont utilisé `CStdioFile` pour les fichiers locaux, mais ces classes vous pouvez gérer les fichiers locaux et les fichiers Internet de façon transparente et cohérente.  
  
 Les classes WinInet MFC fournissent les mêmes fonctionnalités que `CStdioFile` pour les données transférées via Internet. Ces classes convertissent les protocoles Internet pour HTTP, FTP et gopher dans une application de niveau supérieur interface de programmation, en fournissant un chemin d’accès rapide et simple pour la création d’applications Internet. Par exemple, la connexion à un serveur FTP requiert toujours plusieurs étapes de bas niveau, mais en tant que développeur de MFC, vous devez uniquement effectuer un appel à `CInternetSession::GetFTPConnection` pour créer cette connexion.  
  
 En outre, les classes WinInet MFC offrent les avantages suivants :  
  
-   E/s mises en mémoire tampon  
  
-   Descripteurs de type sécurisé pour vos données  
  
-   Paramètres par défaut pour de nombreuses fonctions  
  
-   Gestion des exceptions pour les erreurs Internet courantes  
  
-   Nettoyage automatique des connexions et les descripteurs ouverts  
  
## <a name="see-also"></a>Voir aussi  
 [Extension Internet Win32 (WinInet)](../mfc/win32-internet-extensions-wininet.md)   
 [Comment WinInet facilite la création d’applications clientes Internet](../mfc/how-wininet-makes-it-easier-to-create-internet-client-applications.md)

