---
title: "lock_when, Enum | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "msclr::lock_when"
  - "msclr.lock_when"
  - "lock_when"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "lock_when (enum)"
ms.assetid: 6b87bbe9-63cd-450d-a02e-bb91ffd0dcea
caps.latest.revision: 9
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# lock_when, Enum
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Spécifie un différé le verrouillage.  
  
## Syntaxe  
  
```  
enum lock_when {  
   lock_later  
};  
```  
  
## Notes  
 Lorsque le passage à [lock::lock](../dotnet/lock-lock.md), `lock_later` spécifie que le verrou ne doit pas être pris maintenant.  
  
## Exemple  
 Cet exemple utilise une seule instance d'une classe entre des threads multiples.  La classe utilise un verrou sur elle\-même pour garantir que les accès à ses données internes sont cohérents pour chaque thread.  Le thread d'application principale utilise un verrou sur la même instance de la classe pour vérifier régulièrement si les threads de travail existent toujours, et attend pour quitter jusqu'à ce que tous les threads de travail aient terminé leurs tâches.  
  
```  
// msl_lock_lock_when.cpp  
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
  
 **Espace de noms** msclr  
  
## Voir aussi  
 [verrou](../dotnet/lock.md)