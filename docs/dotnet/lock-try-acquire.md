---
title: "lock::try_acquire | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "try_acquire"
  - "lock.try_acquire"
  - "msclr.lock.try_acquire"
  - "lock::try_acquire"
  - "msclr::lock::try_acquire"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "lock::try_acquire"
ms.assetid: ef0649a9-e611-4495-84bd-2784533221d9
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# lock::try_acquire
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Acquiert un verrou sur un objet, en attendant une quantité spécifique d'heure et retourne `bool` pour indiquer la réussite de l'acquisition au lieu de lever d'exception.  
  
## Syntaxe  
  
```  
bool try_acquire(  
   int _timeout_ms  
);  
bool try_acquire(  
   System::TimeSpan _timeout  
);  
```  
  
#### Paramètres  
 `_timeout`  
 Valeur du délai d'attente en millisecondes ou en tant que <xref:System.TimeSpan>.  
  
## Valeur de retour  
 `true` si le verrou a été acquis ; sinon, `false`.  
  
## Notes  
 Si un verrou a déjà été acquis, cette fonctionnalité n'a aucun effet.  
  
## Exemple  
 Cet exemple utilise une seule instance d'une classe entre des threads multiples.  La classe utilise un verrou sur elle\-même pour garantir que les accès à ses données internes sont cohérents pour chaque thread.  Le thread d'application principale utilise un verrou sur la même instance de la classe pour vérifier régulièrement si les threads de travail existent toujours, et attend pour quitter jusqu'à ce que tous les threads de travail aient terminé leurs tâches.  
  
```  
// msl_lock_try_acquire.cpp  
// compile with: /clr  
#include <msclr/lock.h>  
  
using namespace System;  
using namespace System::Threading;  
using namespace msclr;  
  
ref class CounterClass {  
private:  
   int Counter;     
  
public:  
   property int ThreadCount;  
  
   // function called by multiple threads, use lock to keep Counter consistent  
   // for each thread  
   void UseCounter() {  
      try {  
         lock l(this); // wait infinitely  
  
         Console::WriteLine("In thread {0}, Counter = {1}", Thread::CurrentThread->ManagedThreadId,   
            Counter);  
  
         for (int i = 0; i < 10; i++) {  
            Counter++;  
            Thread::Sleep(10);  
         }  
  
         Console::WriteLine("In thread {0}, Counter = {1}", Thread::CurrentThread->ManagedThreadId,   
            Counter);  
  
         Counter = 0;  
         // lock is automatically released when it goes out of scope and its destructor is called  
      }  
      catch (...) {  
         Console::WriteLine("Couldn't acquire lock!");  
      }  
  
      ThreadCount--;  
   }  
};  
  
int main() {  
   // create a few threads to contend for access to the shared data  
   CounterClass^ cc = gcnew CounterClass;  
   array<Thread^>^ tarr = gcnew array<Thread^>(5);  
   ThreadStart^ startDelegate = gcnew ThreadStart(cc, &CounterClass::UseCounter);  
   for (int i = 0; i < tarr->Length; i++) {  
      tarr[i] = gcnew Thread(startDelegate);  
      cc->ThreadCount++;  
      tarr[i]->Start();  
   }  
  
   // keep our main thread alive until all worker threads have completed  
   lock l(cc, lock_later); // don't lock now, just create the object  
   while (true) {  
      if (l.try_acquire(50)) { // try to acquire lock, don't throw an exception if can't  
         if (0 == cc->ThreadCount) {  
            Console::WriteLine("All threads completed.");  
            break; // all threads are gone, exit while  
         }  
         else {  
            Console::WriteLine("{0} threads exist, continue waiting...", cc->ThreadCount);  
            l.release(); // some threads exist, let them do their work  
         }  
      }  
   }  
}  
```  
  
  **Dans le thread 3, Compteur \= 0**  
**Dans le thread 3, Compteur \= 10**  
**Dans le thread 5, Compteur \= 0**  
**Dans le thread 5, Compteur \= 10**  
**Dans le thread 7, Compteur \= 0**  
**Dans le thread 7, Compteur \= 10**  
**Dans le thread 4, Compteur \= 0**  
**Dans le thread 4, Compteur \= 10**  
**Dans le thread 6, Compteur \= 0**  
**Dans le thread 6, Compteur \= 10**  
**Tous les threads sont terminés.**   
## Configuration requise  
 **Fichier d'en\-tête** \<msclr\\lock.h\>  
  
 **Espace de nommage** msclr  
  
## Voir aussi  
 [lock, membres](../dotnet/lock-members.md)   
 [lock::acquire](../dotnet/lock-acquire.md)