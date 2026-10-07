flowchart LR
    Reader["Оқырман"]
    Librarian["Кітапханашы"]

    subgraph System["Кітапхана жүйесі"]
        Search(["Кітапты іздеу"])
        Borrow(["Кітапты алу"])
        Return(["Кітапты қайтару"])
        Check(["Оқырманды тексеру"])
        Add(["Кітап қосу"])
        Edit(["Кітапты өңдеу"])
        Delete(["Кітапты жою"])
        Register(["Оқырманды тіркеу"])
        Fine(["Айыппұлды есептеу"])
    end

    Reader --- Search
    Reader --- Borrow
    Reader --- Return

    Librarian --- Add
    Librarian --- Edit
    Librarian --- Delete
    Librarian --- Register
    Librarian --- Borrow
    Librarian --- Return

    Borrow -.->|"<<include>>"| Check
    Fine -.->|"<<extend>>"| Return
