---
title: Historique de DCOM | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- Remote Automation, DCOM
- DCOM, about DCOM
- DCOM
ms.assetid: c21aa0ea-1396-4b52-b77f-88fb0fdd2a5c
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 6ef567c39c93c3d43fdfc0fa63886144b03cd474
ms.sourcegitcommit: fa7a6dccddce3747389c91277a53e296f905305c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2018
---
# <a name="history-of-dcom"></a>Historique de DCOM
Lors de l’Automation a été introduite dans 1993 anticipée, il a été pouvant être utilisé qu’entre des applications en cours d’exécution sur le même ordinateur. Toutefois, car elle partageait les mêmes que le reste des OLE, c'est-à-dire, COM (Component Object Model), il a toujours été prévu qu’elle devient « distant » lorsque COM lui-même a été mis à jour pour inclure des fonctionnalités de communication à distance. Il est également prévu que la transition d’un fonctionnement local fonctionnement distribué nécessiterait peu ou aucune modification au code existant.  
  
 Afin que « remoting » signifie COM Local stipulé que le consommateur d’une interface réside et d’exécution sur le même ordinateur que le fournisseur de cette interface. Par exemple, Microsoft Visual Basic peut contrôler une copie de Microsoft Excel sur votre ordinateur de bureau, mais il n’était pas capable de diriger l’exécution d’Excel sur un autre ordinateur. Avec le développement du modèle COM distribué, le consommateur d’une interface n’a plus besoin de résider sur le même ordinateur que celui sur lequel s’exécute le fournisseur d’interface.  
  
 Une fois que COM a été adapté pour fonctionner sur un réseau, puis n’importe quelle interface qui n’était pas liée à un modèle d’exécution local (certaines interfaces ont dépendent des fonctionnalités de l’ordinateur local, telles que celles dessin interfaces dont méthodes ont des descripteurs de contextes de périphérique en tant que paramètres) seraient peut-elle être distribuée. Un consommateur d’interface rendrait une demande pour une interface donnée ; Cette interface peut être fournie par une instance d’un objet en cours d’exécution (ou à exécuter) sur un autre ordinateur. Le mécanisme de distribution à l’intérieur de COM connecte le consommateur au fournisseur de telle sorte que les appels de méthode effectuées par le consommateur apparaît à la fin du fournisseur, où elles sont exécutées. Les valeurs sont ensuite renvoyées au consommateur de retour. Pour tous les cas, le fait de distribution est transparent pour le consommateur et le fournisseur.  
  
 Une telle variété de COM existe désormais. DCOM (pour « modèle COM distribué ») est fournie avec les versions de Windows NT à partir de la version 4.0 et avec Windows 2000. Depuis la fin de 1996, il a été disponible pour Windows 9 x. Dans les deux cas, DCOM comprend un ensemble de DLL supplémentaires et de remplacement avec certains utilitaires, qui fournissent des fonctionnalités COM locales et distantes. Il est donc désormais partie intégrante de plateformes Win32 et sera disponible sur d’autres plateformes par d’autres organisations au fil du temps.  
  
## <a name="in-this-section"></a>Dans cette section  
 [Quand l’Automation à distance se convient-elle](where-does-remote-automation-fit-in-q.md)  
  
 [Que fournit l’Automation à distance](what-does-remote-automation-provide-q.md)  
  
## <a name="see-also"></a>Voir aussi  
 [Automation à distance](../mfc/remote-automation.md)
