<script lang="ts">
  import Hero from "$lib/components/Hero.svelte";
  import SectorList from "$lib/components/SectorList.svelte";
  import FeatureSection from "$lib/components/FeatureSection.svelte";
  import ClientsSection from "$lib/components/ClientsSection.svelte";
  import PlatformBadges from "$lib/components/PlatformBadges.svelte";
  import Footer from "$lib/components/Footer.svelte";

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
  };

  const sectorTitle = "Ngành nghề KiotViet đồng hành";

  const sectorDescription =
    "Dù bạn vận hành cửa hàng bán lẻ, chuỗi F&amp;B hay kho phân phối, bố cục này giúp giới thiệu nhanh các ngành kinh doanh được hỗ trợ.";

  const sectors = [
    {
      title: "Bán lẻ & chuỗi cửa hàng",
      description:
        "Đồng bộ dữ liệu tồn kho, chuyển hàng liên chi nhánh và quản lý giá linh hoạt.",
    },
    {
      title: "F&B & giải trí",
      description:
        "Sơ đồ bàn, tính giờ, combo linh hoạt cùng báo cáo doanh thu từng khung giờ.",
    },
    {
      title: "Nhà phân phối & bán buôn",
      description:
        "Quản lý đơn hàng số lượng lớn, công nợ đối tác và báo cáo lợi nhuận theo SKU.",
    },
    {
      title: "Dịch vụ & chăm sóc",
      description:
        "Theo dõi lịch hẹn, hồ sơ khách hàng và nhắc lịch tự động qua SMS hoặc Zalo.",
    },
    {
      title: "Thương mại điện tử",
      description:
        "Đồng bộ sản phẩm từ sàn, xử lý đơn tự động và đối soát phí ship nhanh chóng.",
    },
    {
      title: "Siêu thị & minimart",
      description:
        "Tương thích mã vạch, quy đổi đơn vị và kiểm kho bằng thiết bị di động.",
    },
  ];

  const features = [
    {
      title: "Quản lý vận hành đơn giản và chính xác",
      description:
        "Thiết kế thân thiện giúp bạn thao tác chỉ trong vài bước, phù hợp cho cả nhân viên mới.",
      bullets: [
        "Dashboard tổng quan theo thời gian thực.",
        "Quản lý hàng hóa, tồn kho và serial linh hoạt.",
        "Phân quyền nhân sự, lịch làm việc và chấm công.",
        "Báo cáo đa chiều với hơn 30 biểu mẫu chuẩn.",
      ],
      imageLabel: "Trung tâm điều hành",
      reverse: false,
    },
    {
      title: "Bán hàng đa kênh, đồng bộ mọi điểm chạm",
      description:
        "Tăng tốc doanh số khi đồng bộ cửa hàng, sàn thương mại và các kênh mạng xã hội trên một nền tảng.",
      bullets: [
        "Kết nối Shopee, Lazada, TikTok Shop chỉ với vài cú nhấp.",
        "Theo dõi đơn online/offline tại một nơi.",
        "Đồng bộ chương trình khuyến mãi giữa các kênh.",
        "Ứng dụng quản lý trên di động cho chủ shop.",
      ],
      imageLabel: "Bảng điều khiển đa kênh",
      reverse: true,
    },
  ];

  const testimonial = {
    quote:
      "“Từ khi triển khai, việc kiểm soát tồn kho và báo cáo doanh thu theo chi nhánh chỉ mất vài phút. Đội ngũ hỗ trợ nhiệt tình giúp tôi mở thêm 4 cửa hàng trong 6 tháng.”",
    author: "Nguyễn Minh Anh",
    role: "Chuỗi cửa hàng thời trang Luma",
  };

  const logos = [
    "Luma Shop",
    "Fresh Mart",
    "88 Coffee",
    "GoSport",
    "An Khang Spa",
    "TechOne",
  ];
</script>

<Hero {...heroData} />

<SectorList {sectorTitle} {sectorDescription} {sectors} />

{#each features as feature (feature.title)}
  <FeatureSection {...feature} />
{/each}

<ClientsSection {...testimonial} {logos} />

<Footer />
