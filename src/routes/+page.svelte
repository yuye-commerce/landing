<script lang="ts">
  import Hero from "$lib/components/Hero.svelte";
  import SectorList from "$lib/components/SectorList.svelte";
  import Footer from "$lib/components/Footer.svelte";
  import Benefits from "$lib/components/Benefits.svelte";
  import ClientSection from "$lib/components/ClientsSection.svelte";

  import Package from "@lucide/svelte/icons/package";
  import FileText from "@lucide/svelte/icons/file-text";
  import BarChart3 from "@lucide/svelte/icons/bar-chart-3";
  import Users from "@lucide/svelte/icons/users";
  import UserCog from "@lucide/svelte/icons/user-cog";
  import CreditCard from "@lucide/svelte/icons/credit-card";
  import RefreshCw from "@lucide/svelte/icons/refresh-cw";
  import Tag from "@lucide/svelte/icons/tag";
  import MousePointerClick from "@lucide/svelte/icons/mouse-pointer-click";
  import Coffee from "@lucide/svelte/icons/coffee";
  import Building2 from "@lucide/svelte/icons/building-2";

  import Shirt from "@lucide/svelte/icons/shirt";
  import ShoppingBasket from "@lucide/svelte/icons/shopping-basket";
  import Smartphone from "@lucide/svelte/icons/smartphone";
  import Sparkles from "@lucide/svelte/icons/sparkles";
  import Hammer from "@lucide/svelte/icons/hammer";
  import Leaf from "@lucide/svelte/icons/leaf";
  import Pill from "@lucide/svelte/icons/pill";
  import Truck from "@lucide/svelte/icons/truck";
  import Baby from "@lucide/svelte/icons/baby";
  import Sofa from "@lucide/svelte/icons/sofa";
  import Book from "@lucide/svelte/icons/book";
  import Gift from "@lucide/svelte/icons/gift";
  import Factory from "@lucide/svelte/icons/factory";
  import MoreHorizontal from "@lucide/svelte/icons/more-horizontal";

  const heroData = {
    highlight: "Giải pháp quản lý bán hàng toàn diện",
    headline: "Phần mềm quản lý bán hàng phổ biến nhất",
    subheadline:
      "Tự động hóa quy trình, đồng bộ tồn kho và theo dõi doanh thu theo thời gian thực ở mọi điểm bán.",
    ctaText: "Dùng thử miễn phí",
    ctaHref: "#dang-ky",
    secondaryCta: {
      text: "Khám phá sản phẩm",
      href: "#tinh-nang",
    },
    heroStats: [
      { label: "Doanh nghiệp tin dùng", value: "150.000+" },
      { label: "Mức độ hài lòng", value: "98%" },
      { label: "Thời gian triển khai", value: "3 ngày" },
    ],
    heroFunctions: [
      { icon: Package, title: "Quản lý kho hàng" },
      { icon: FileText, title: "Quản lý hoá đơn" },
      { icon: BarChart3, title: "Báo cáo doanh thu" },
      { icon: Users, title: "Quản lý khách hàng" },
      { icon: UserCog, title: "Quản lý nhân viên" },
      { icon: CreditCard, title: "Thanh toán đa hình thức" },
      { icon: RefreshCw, title: "Đồng bộ đa chi nhánh" },
      { icon: Tag, title: "Quản lý khuyến mãi" },
    ],
  };

  const benefitData = {
    header: "HaloPOS giúp bạn quản lý dễ dàng, bán hàng hiệu quả",
    benefits: [
      {
        icon: MousePointerClick,
        title: "Đơn giản & Dễ sử dụng",
        description:
          "Đồng bộ dữ liệu tồn kho, chuyển hàng liên chi nhánh và quản lý giá linh hoạt.",
      },
      {
        icon: Coffee,
        title: "F&B & giải trí",
        description:
          "Sơ đồ bàn, tính giờ, combo linh hoạt cùng báo cáo doanh thu từng khung giờ.",
      },
      {
        icon: Building2,
        title: "Nhà phân phối & bán buôn",
        description:
          "Quản lý đơn hàng số lượng lớn, công nợ đối tác và báo cáo lợi nhuận theo SKU.",
      },
    ],
  };

  const sectorData = {
    title:
      "HaloPOS thiết kế phần mềm quản lý bán hàng chuyên biệt cho từng ngành hàng",
    description:
      "Dù bạn vận hành cửa hàng bán lẻ, chuỗi F&amp;B hay kho phân phối, bố cục này giúp giới thiệu nhanh các ngành kinh doanh được hỗ trợ.",
    sectors: [
      {
        title: "Thời trang",
        icon: Shirt,
      },
      {
        title: "Tạp hóa & Siêu thị",
        icon: ShoppingBasket,
      },
      {
        title: "Điện thoại & Điện máy",
        icon: Smartphone,
      },
      {
        title: "Mỹ phẩm",
        icon: Sparkles,
      },
      {
        title: "Vật liệu xây dựng",
        icon: Hammer,
      },
      {
        title: "Nông sản & Thực phẩm",
        icon: Leaf,
      },
      {
        title: "Nhà thuốc",
        icon: Pill,
      },
      {
        title: "Xe, Máy móc",
        icon: Truck,
      },
      {
        title: "Mẹ & Bé",
        icon: Baby,
      },
      {
        title: "Nội thất & Gia dụng",
        icon: Sofa,
      },
      {
        title: "Sách & Văn phòng phẩm",
        icon: Book,
      },
      {
        title: "Hoa & Quà tặng",
        icon: Gift,
      },
      {
        title: "Sản xuất",
        icon: Factory,
      },
      {
        title: "Khác",
        icon: MoreHorizontal,
      },
    ],
  };

  const clientData = {
    title: "Khách hàng của chúng tôi",
    clients: [
      {
        src: "https://placecats.com/400/400",
        name: "Quán A",
        desc: "Cửa hàng thời trang Luma",
      },
      {
        src: "https://placecats.com/400/400",
        name: "Quán A",
        desc: "Cửa hàng thời trang Luma",
      },
      {
        src: "https://placecats.com/400/400",
        name: "Quán A",
        desc: "Cửa hàng thời trang Luma",
      },
      {
        src: "https://placecats.com/400/400",
        name: "Quán A",
        desc: "Cửa hàng thời trang Luma",
      },
    ],
  };
</script>

<Hero {...heroData} />

<Benefits {benefitData} />

<SectorList {sectorData} />

<ClientSection {clientData} />

<Footer />
