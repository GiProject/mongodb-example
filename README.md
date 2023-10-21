```
    const db = client.db('test');
    const booksCollection = db.collection('books');

    booksCollection.insertMany([{
            title: "Book 1",
            description: "Book description",
            authors: "Author"
        }, {
            title: "Book 2",
            description: "Book description",
            authors: "Author"
        },
    ])
    
    const book = await booksCollection.findOne({
        title: /^Book/
    });

    booksCollection.updateOne({
        _id: book._id
    }, {
        $set: {
            "description": "update description",
            "authors": "update authors"
        }
    })

    const updateBook = await booksCollection.findOne({
        _id: book._id
    });
```
