import React from "react"; import { Card, CardContent } from "@/components/ui/card"; import { Button } from "@/components/ui/button"; import { ShoppingCart } from "lucide-react";

const products = [ { id: 1, name: "Relógio Minimalista", price: "R$ 149,90", image: "https://via.placeholder.com/300x200", }, { id: 2, name: "Fone Bluetooth", price: "R$ 199,90", image: "https://via.placeholder.com/300x200", }, { id: 3, name: "Mochila Executiva", price: "R$ 229,90", image: "https://via.placeholder.com/300x200", }, ];

export default function LojaOnline() { return ( <div className="min-h-screen bg-gray-100 p-6"> <header className="flex justify-between items-center mb-8"> <h1 className="text-3xl font-bold">Minha Loja Online</h1> <Button className="flex items-center gap-2 rounded-2xl"> <ShoppingCart size={18} /> Carrinho </Button> </header>

<section className="grid md:grid-cols-3 gap-6">
    {products.map((product) => (
      <Card key={product.id} className="rounded-2xl shadow-lg">
        <img
          src={product.image}
          alt={product.name}
          className="rounded-t-2xl w-full h-48 object-cover"
        />
        <CardContent className="p-4">
          <h2 className="text-xl font-semibold mb-2">{product.name}</h2>
          <p className="text-gray-600 mb-4">{product.price}</p>
          <Button className="w-full rounded-2xl">Comprar</Button>
        </CardContent>
      </Card>
    ))}
  </section>

  <footer className="mt-12 text-center text-gray-500">
    © {new Date().getFullYear()} Minha Loja Online - Todos os direitos reservados.
  </footer>
</div>

); }
