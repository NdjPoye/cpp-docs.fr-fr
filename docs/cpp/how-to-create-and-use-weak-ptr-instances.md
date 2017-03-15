---
title: "Comment&#160;: cr&#233;er et utiliser des instances weak_ptr | Microsoft Docs"
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
ms.assetid: 8dd6909b-b070-4afa-9696-f2fc94579c65
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# Comment&#160;: cr&#233;er et utiliser des instances weak_ptr
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Parfois, un objet doit stocker le moyen d'accéder à l'objet sous\-jacent de `shared_ptr` sans provoquer l'incrémentation du décompte de références.  En général, cette situation se produit lorsque vous avez des références cycliques entre des instances `shared_ptr`.  
  
 Le mieux est d'éviter le partage de propriété des pointeurs, chaque fois que cela est possible.  Toutefois, si vous avez besoin d'avoir la propriété partagée des instances `shared_ptr`, évitez les références cycliques entre elles.  Lorsque les références cycliques sont inévitables, voire préférables pour une raison quelconque, utilisez `weak_ptr` pour donner à un ou plusieurs propriétaires une référence faible à un autre `shared_ptr`.  En utilisant un `weak_ptr`, vous pouvez créer un `shared_ptr` qui rejoint un ensemble existant d'instances connexes, mais uniquement si la ressource de mémoire sous\-jacente est encore valide.  Un `weak_ptr` lui\-même ne participe pas au décompte de références. Par conséquent, il ne peut pas empêcher le décompte de références d'atteindre zéro.  Toutefois, vous pouvez utiliser `weak_ptr` pour essayer d'obtenir une nouvelle copie de `shared_ptr` qui a servi à l'initialiser.  Si la mémoire a déjà été supprimée, une exception **bad\_weak\_ptr** est levée.  Si la mémoire est encore valide, le nouveau pointeur partagé incrémente le décompte de références et garantit que la mémoire sera valide tant que la variable `shared_ptr` reste dans la portée.  
  
## Exemple  
 L'exemple de code suivant illustre un cas où `weak_ptr` est utilisé pour garantir la suppression appropriée des objets qui ont des dépendances circulaires.  En examinant l'exemple, supposez qu'il a été créé uniquement après la prise en compte de solutions alternatives.  Les objets `Controller` représentent un aspect d'un processus d'ordinateur et fonctionnent indépendamment.  Chaque contrôleur doit pouvoir vérifier l'état des autres contrôleurs à tout moment, et chacun contient un `vector<weak_ptr<Controller>>` privé à cet effet.  Chaque vecteur contient une référence circulaire, et les instances de `weak_ptr` sont donc utilisées au lieu de `shared_ptr`.  
  
 [!code-cpp[stl_smart_pointers#222](../cpp/codesnippet/CPP/how-to-create-and-use-weak-ptr-instances_1.cpp)]  
  
  **Création de Controller0**  
**Création de Controller1**  
**Création de Controller2**  
**Création de Controller3**  
**Création de Controller4**  
**push\_back to v\[0\]: 1**  
**push\_back to v\[0\]: 2**  
**push\_back to v\[0\]: 3**  
**push\_back to v\[0\]: 4**  
**push\_back to v\[1\]: 0**  
**push\_back to v\[1\]: 2**  
**push\_back to v\[1\]: 3**  
**push\_back to v\[1\]: 4**  
**push\_back to v\[2\]: 0**  
**push\_back to v\[2\]: 1**  
**push\_back to v\[2\]: 3**  
**push\_back to v\[2\]: 4**  
**push\_back to v\[3\]: 0**  
**push\_back to v\[3\]: 1**  
**push\_back to v\[3\]: 2**  
**push\_back to v\[3\]: 4**  
**push\_back to v\[4\]: 0**  
**push\_back to v\[4\]: 1**  
**push\_back to v\[4\]: 2**  
**push\_back to v\[4\]: 3**  
**use\_count \= 1**  
**État de 1 \= Activé**  
**État de 2 \= Activé**  
**État de 3 \= Activé**  
**État de 4 \= Activé**  
**use\_count \= 1**  
**État de 0 \= Activé**  
**État de 2 \= Activé**  
**État de 3 \= Activé**  
**État de 4 \= Activé**  
**use\_count \= 1**  
**État de 0 \= Activé**  
**État de 1 \= Activé**  
**État de 3 \= Activé**  
**État de 4 \= Activé**  
**use\_count \= 1**  
**État de 0 \= Activé**  
**État de 1 \= Activé**  
**État de 2 \= Activé**  
**État de 4 \= Activé**  
**use\_count \= 1**  
**État de 0 \= Activé**  
**État de 1 \= Activé**  
**État de 2 \= Activé**  
**État de 3 \= Activé**  
**Destruction de Controller0**  
**Destruction de Controller1**  
**Destruction de Controller2**  
**Destruction de Controller3**  
**Destruction de Controller4**  
**Appuyez sur une touche** À titre d'expérimentation, remplacez le vecteur `others` par un `vector<shared_ptr<Controller>>`, puis dans la sortie, notez qu'aucun destructeur n'est appelé lorsque `TestRun` est retourné.  
  
## Voir aussi  
 [Pointeurs intelligents](../cpp/smart-pointers-modern-cpp.md)