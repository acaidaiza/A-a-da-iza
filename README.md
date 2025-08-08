const menuSections = [ { id: 'entradas', title: 'Entradas', items: [ { name: 'Coxinha (3 un.)', desc: 'Massa crocante e recheio cremoso de frango.', price: 'R$ 12,00' }, { name: 'Bolinho de queijo (4 un.)', desc: 'Queijo derretido e fritura dourada.', price: 'R$ 14,00' } ] }, { id: 'principais', title: 'Pratos Principais', items: [ { name: 'X-salada completo', desc: 'Pão artesanal, carne 150g, queijo, alface e tomate.', price: 'R$ 24,00' }, { name: 'Estrogonofe de frango', desc: 'Arroz branco e batata palha inclusos.', price: 'R$ 28,00' } ] }, { id: 'bebidas', title: 'Bebidas', items: [ { name: 'Refrigerante 350ml', desc: 'Lata gelada.', price: 'R$ 6,00' }, { name: 'Suco natural 300ml', desc: 'Feito na hora.', price: 'R$ 8,00' } ] }, { id: 'sobremesas', title: 'Sobremesas', items: [ { name: 'Brigadeiro de colher', desc: 'Doce tradicional.', price: 'R$ 6,00' }, { name: 'Pudim da casa', desc: 'Pudim cremoso com calda de caramelo.', price: 'R$ 10,00' } ] } ];

export default function CardapioSite() { return ( <div className="min-h-screen bg-gray-50 text-gray-900"> <header className="bg-white shadow"> <div className="max-w-5xl mx-auto px-6 py-6 flex items-center justify-between"> <div className="flex items-center gap-4"> <div className="w-12 h-12 bg-yellow-400 rounded-full flex items-center justify-center font-bold text-white">C</div> <div> <h1 className="text-2xl font-extrabold">Cardápio — Casa do Sabor</h1> <p className="text-sm text-gray-500">Comida afetiva, feita com carinho</p> </div> </div>

<nav className="hidden md:flex gap-4 items-center">
        {menuSections.map(s => (
          <a key={s.id} href={`#${s.id}`} className="text-sm hover:text-yellow-600">{s.title}</a>
        ))}
        <a href="#pedido" className="ml-4 inline-block px-4 py-2 bg-yellow-500 text-white rounded-lg font-semibold">Pedir</a>
      </nav>

      <div className="md:hidden">
        <a href="#pedido" className="inline-block px-3 py-2 bg-yellow-500 text-white rounded-lg font-semibold text-sm">Pedir</a>
      </div>
    </div>
  </header>

  <main className="max-w-5xl mx-auto px-6 py-10">
    <section className="grid grid-cols-1 md:grid-cols-2 gap-6 items-center">
      <div>
        <h2 className="text-3xl font-extrabold mb-3">Bem-vindo ao nosso cardápio</h2>
        <p className="text-gray-600 mb-4">Escolha entre entradas crocantes, pratos principais suculentos, bebidas geladas e sobremesas irresistíveis. Toques caseiros em cada receita.</p>
        <div className="flex gap-3">
          <a href="#principais" className="px-4 py-2 bg-yellow-500 text-white rounded-lg font-medium">Ver pratos</a>
          <a href="#contato" className="px-4 py-2 border border-gray-200 rounded-lg">Contato</a>
        </div>
      </div>

      <div className="rounded-xl overflow-hidden shadow-lg">
        <img src="https://images.unsplash.com/photo-1604908177522-7bd02f3b6b5b?q=80&w=1200&auto=format&fit=crop&ixlib=rb-4.0.3&s=placeholder" alt="Prato destaque" className="w-full h-64 object-cover"/>
      </div>
    </section>

    <section className="mt-10">
      {menuSections.map(section => (
        <div id={section.id} key={section.id} className="mb-10">
          <h3 className="text-2xl font-bold mb-4">{section.title}</h3>
          <div className="grid grid-cols-1 md:grid-cols-2 gap-4">
            {section.items.map((it, idx) => (
              <div key={idx} className="flex items-start gap-4 p-4 bg-white rounded-lg shadow-sm">
                <div className="w-20 h-20 bg-gray-100 rounded-lg flex items-center justify-center text-sm text-gray-500">Imagem</div>
                <div className="flex-1">
                  <div className="flex items-center justify-between">
                    <h4 className="font-semibold">{it.name}</h4>
                    <span className="font-semibold">{it.price}</span>
                  </div>
                  <p className="text-sm text-gray-500 mt-1">{it.desc}</p>
                  <div className="mt-3 flex gap-2">
                    <button className="px-3 py-1 border border-yellow-500 text-yellow-600 rounded-md text-sm">Adicionar</button>
                    <button className="px-3 py-1 bg-yellow-500 text-white rounded-md text-sm">Pedir</button>
                  </div>
                </div>
              </div>
            ))}
          </div>
        </div>
      ))}
    </section>

    <section id="pedido" className="mt-6 p-6 bg-white rounded-lg shadow text-gray-800">
      <h3 className="text-xl font-bold mb-3">Fazer um pedido</h3>
      <p className="text-sm text-gray-600 mb-4">Envie seu pedido pelo WhatsApp ou telefone. Preencha o formulário abaixo e entraremos em contato.</p>

      <form className="grid grid-cols-1 md:grid-cols-2 gap-4">
        <input placeholder="Seu nome" className="p-3 border rounded" />
        <input placeholder="Telefone (WhatsApp)" className="p-3 border rounded" />
        <input placeholder="Endereço (opcional)" className="p-3 border rounded md:col-span-2" />
        <textarea placeholder="Escreva seu pedido aqui (ex: 2x Coxinha, 1x X-salada)" className="p-3 border rounded md:col-span-2" rows={4}></textarea>
        <div className="md:col-span-2 flex gap-3">
          <button type="button" className="px-4 py-2 bg-yellow-500 text-white rounded font-semibold">Enviar pedido</button>
          <a href="https://wa.me/5511999999999?text=Olá%20quero%20fazer%20um%20pedido" target="_blank" rel="noreferrer" className="px-4 py-2 border rounded">Pedir por WhatsApp</a>
        </div>
      </form>
    </section>

    <section id="contato" className="mt-10 text-sm text-gray-600">
      <h4 className="font-bold">Contato</h4>
      <p>Telefone/WhatsApp: <a href="tel:+5511999999999" className="text-yellow-600">(11) 99999-9999</a></p>
      <p>Endereço: Rua Exemplo, 123 — Bairro, Cidade</p>
      <p className="mt-2">Horário: Seg–Sex 11:00–22:00 • Sáb 11:00–18:00</p>
    </section>
  </main>

  <footer className="mt-12 bg-white border-t">
    <div className="max-w-5xl mx-auto px-6 py-6 text-center text-sm text-gray-500">© {new Date().getFullYear()} Casa do Sabor — Feito com ♥</div>
  </footer>
</div>

); }

