## What is Docker?

* Relies on Linux kernel <!-- .element: class="fragment" -->
    * Namespace isolation <!-- .element: class="fragment" -->
    (PID, mount, user, network isolation)
    * cgropus <!-- .element: class="fragment" -->
    (CPU, memory, disk I/O isolation)
    * chroot <!-- .element: class="fragment" -->
    (File system isolation)

* Use AUFS <!-- .element: class="fragment" --> (AnotherUnionFs -> advanced multilayered unification filesystem) http://en.wikipedia.org/wiki/Aufs
    * Layered FS <!-- .element: class="fragment" -->
    * Share common FS <!-- .element: class="fragment" -->

* Encapsulation <!-- .element: class="fragment" --> 

* Portability <!-- .element: class="fragment" --> 

* Lightweight <!-- .element: class="fragment" --> 

note:
    **Nampespace**: se separan grupos de procesos de manera que no pueden ver los procesos de otros grupos.
    Por ejemlo, un namespace para PID hace que los procesos dentro del namespace tengan diferente numeración.
    **cgropus**: aislan los recursos como la CPU, la memoria, I/O y red.