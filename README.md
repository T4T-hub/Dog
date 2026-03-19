<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Productpagina</title>
    <script src="https://unpkg.com/react@18/umd/react.development.js"></script>
    <script src="https://unpkg.com/react-dom@18/umd/react-dom.development.js"></script>
    <script src="https://unpkg.com/babel-standalone@6/babel.min.js"></script>
    <style>
      body {
        font-family: sans-serif;
        padding: 20px;
        background: #f8f8f8;
      }

      .product {
        background: white;
        padding: 16px;
        margin-bottom: 12px;
        border-radius: 6px;
        box-shadow: 0 0 6px rgba(0, 0, 0, 0.1);
      }

      .product h2 {
        margin: 0 0 8px;
      }

      .product p {
        margin: 0;
      }
    </style>
  </head>

  <body>
    <div id="root"></div>

    <script type="text/babel">
      const producten = [
        { id: 1, naam: "Hondenvoer Premium", prijs: "€29,95" },
        { id: 2, naam: "Krabpaal XL", prijs: "€59,95" },
        { id: 3, naam: "Pluche eendje", prijs: "€7,95" },
        { id: 4, naam: "banaan", prijs: "5" },
      ];

      function Product({ naam, prijs }) {
        return (
          <div className="product">
            <h2>{naam}</h2>
            <p>Prijs: {prijs}</p>
          </div>
        );
      }

      function App() {
        return (
          <div>
            <h1>Onze producten</h1>
            {producten.map((p) => (
              <Product key={p.id} naam={p.naam} prijs={p.prijs} />
            ))}
          </div>
        );
      }

      const root = document.getElementById("root");
      ReactDOM.render(<App />, root);
    </script>
  </body>
</html>
