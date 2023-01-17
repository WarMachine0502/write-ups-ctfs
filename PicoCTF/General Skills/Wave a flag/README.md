## **Wave a flag**  
We have a file named `warm`, which does not give out human-readable values when we browse its contents through ``cat``. Hence we check the filetype of ``warm``, which reveals that it is a 64-bit executable file. Hence we give it executable privileges using the ``chmod +x warm`` command and then try and run it using ``./warm``. This gives us further instructions on what arguments is required by the file, and we finally get the flag after running ``./warm -h``.

>> flag: picoCTF{b1scu1ts_4nd_gr4vy_6635aa47}

![screenshot_of_solution](https://lh5.googleusercontent.com/qv3WcK9DU7D_BGVp8nKrwBcIhKQ2fQ-kKJTytRzMhRFL8fLvPsvXcYWCBgIdooptSac=w2400)
