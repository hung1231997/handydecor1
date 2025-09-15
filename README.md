# handydecor1
import React, { useState } from "react";


<div className="mt-6 grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 lg:grid-cols-4 gap-6">
{filtered.map(p => (
<div key={p.id} className="bg-white rounded-lg overflow-hidden shadow-sm">
<img src={p.img} alt={p.title} className="h-40 w-full object-cover" />
<div className="p-4">
<h3 className="font-semibold">{p.title}</h3>
<p className="mt-2 text-indigo-600 font-semibold">{p.price}</p>
<div className="mt-4 flex gap-2">
<button onClick={() => setSelected(p)} className="flex-1 border rounded-md px-3 py-2 text-sm">Xem</button>
<button onClick={() => addToCart(p)} className="bg-indigo-600 text-white rounded-md px-3 py-2 text-sm">Thêm vào giỏ</button>
</div>
</div>
</div>
))}
</div>
</section>


{/* About */}
<section id="about" className="max-w-7xl mx-auto px-4 py-12 grid md:grid-cols-2 gap-8 items-center">
<div>
<h2 className="text-3xl font-bold">Về HandyDecor</h2>
<p className="mt-4 text-gray-600">Chúng tôi chọn lọc những món đồ nội thất và trang trí thủ công, tập trung vào chất lượng, thẩm mỹ và bền vững. Mỗi sản phẩm đều được kiểm tra kỹ lưỡng trước khi giao đến tay khách hàng.</p>
<ul className="mt-4 space-y-2 text-sm text-gray-600">
<li>• Sản phẩm thủ công & thiết kế độc đáo</li>
<li>• Chính sách hoàn trả trong 7 ngày</li>
<li>• Hỗ trợ tư vấn bài trí miễn phí</li>
</ul>
</div>
<div>
<img src="https://images.unsplash.com/photo-1505691723518-36a5b9bd0a6e?auto=format&fit=crop&w=1200&q=60" alt="about" className="rounded-lg shadow-md w-full object-cover h-72" />
</div>
</section>


{/* Footer */}
<footer id="contact" className="bg-gray-900 text-gray-200">
<div className="max-w-7xl mx-auto px-4 py-12 grid md:grid-cols-3 gap-8">
<div>
<div className="text-2xl font-bold">HandyDecor</div>
<p className="mt-3 text-sm text-gray-400">Địa chỉ giả định • Số điện thoại • email@example.com</p>
</div>
<div>
<h4 className="font-semibold">Liên kết</h4>
<ul className="mt-3 space-y-2 text-sm text-gray-400">
<li>Chính sách vận chuyển</li>
<li>Điều khoản sử dụng</li>
<li>Hỗ trợ khách hàng</li>
</ul>
</div>
<div>
<h4 className="font-semibold">Đăng ký nhận tin</h4>
<p className="text-sm text-gray-400 mt-2">Nhập email để nhận khuyến mãi và tin tức.</p>
<div className="mt-3 flex gap-2">
<input className="flex-1 px-3 py-2 rounded-md text-gray-800" placeholder="email@example.com" />
<button className="bg-indigo-600 px-4 py-2 rounded-md">Gửi</button>
</div>
</div>
</div>
<div className="border-t border-gray-800 text-center text-sm py-4">© {new Date().getFullYear()} HandyDecor - Mẫu demo</div>
</footer>


{/* Modal product detail */}
{selected && (
<div className="fixed inset-0 bg-black/50 flex items-center justify-center z-50">
<div className="bg-white rounded-lg max-w-2xl w-full overflow-hidden">
<div className="flex justify-between items-start p-4">
<h3 className="font-bold">{selected.title}</h3>
<button onClick={() => setSelected(null)} className="text-gray-500">Đóng</button>
</div>
<div className="p-4 grid md:grid-cols-2 gap-4">
<img src={selected.img} alt={selected.title} className="w-full h-64 object-cover rounded" />
<div>
<p className="text-indigo-600 font-semibold">{selected.price}</p>
<p className="mt-3 text-gray-600">Mô tả ngắn về sản phẩm. Thay nội dung này bằng mô tả thật của bạn.</p>
<div className="mt-6 flex gap-2">
<button onClick={() => { addToCart(selected); setSelected(null); }} className="bg-indigo-600 text-white px-4 py-2 rounded-md">Thêm vào giỏ</button>
<button onClick={() => setSelected(null)} className="border px-4 py-2 rounded-md">Đóng</button>
</div>
</div>
</div>
</div>
</div>
)}
</div>
);
}
