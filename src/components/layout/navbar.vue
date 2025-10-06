<template>
  <nav class="navbar navbar-expand-lg bg-white">
    <div class="container">
      <a class="navbar-brand fw-bold" href="#">Logo</a>

      <button
        class="navbar-toggler"
        type="button"
        data-bs-toggle="collapse"
        data-bs-target="#mainNavbar"
        aria-controls="mainNavbar"
        aria-expanded="false"
        aria-label="Toggle navigation"
      >
        <span class="navbar-toggler-icon"></span>
      </button>

      <div class="collapse navbar-collapse" id="mainNavbar">
        <ul
          class="navbar-nav mx-lg-auto gap-lg-3 mb-2 mb-lg-0 align-items-lg-center"
        >
          <li
            v-for="(group, gi) in dropdownGroups"
            :key="`dd-${gi}`"
            class="nav-item dropdown"
          >
            <a
              class="nav-link dropdown-toggle d-flex align-items-center gap-1 fw-semibold text-dark"
              href="#"
              role="button"
              data-bs-toggle="dropdown"
              aria-expanded="false"
            >
              {{ group.label }}
            </a>
            <ul class="dropdown-menu">
              <li v-for="(item, ii) in group.items" :key="`ddi-${gi}-${ii}`">
                <a class="dropdown-item" :href="item.href">{{ item.label }}</a>
              </li>
            </ul>
          </li>
          <li class="nav-item">
            <a class="nav-link fw-semibold text-dark" :href="singleLink.href">{{
              singleLink.label
            }}</a>
          </li>
        </ul>

        <div class="d-flex align-items-center gap-3">
          <a
            href="#"
            class="d-flex align-items-center text-decoration-none text-dark"
          >
            <span class="text-primary me-2 d-inline-flex align-items-center">
              <!-- person -->
              <svg
                width="20"
                height="20"
                viewBox="0 0 16 16"
                fill="currentColor"
                xmlns="http://www.w3.org/2000/svg"
              >
                <path
                  d="M8 8a3 3 0 1 0 0-6 3 3 0 0 0 0 6Z"
                  fill="none"
                  stroke="currentColor"
                  stroke-width="1.5"
                />
                <path
                  d="M2 14c0-2.761 2.686-4 6-4s6 1.239 6 4"
                  fill="none"
                  stroke="currentColor"
                  stroke-width="1.5"
                  stroke-linecap="round"
                />
              </svg>
            </span>
            <span class="fw-medium">Login</span>
          </a>

          <button type="button" class="btn btn-link text-dark p-0">
            <!-- search -->
            <svg
              width="20"
              height="20"
              viewBox="0 0 16 16"
              fill="currentColor"
              xmlns="http://www.w3.org/2000/svg"
            >
              <circle
                cx="6.5"
                cy="6.5"
                r="5.5"
                fill="none"
                stroke="currentColor"
                stroke-width="1.5"
              />
              <path
                d="M11 11l4 4"
                stroke="currentColor"
                stroke-width="1.5"
                stroke-linecap="round"
              />
            </svg>
          </button>

          <span class="vr d-none d-lg-inline"></span>

          <button
            type="button"
            class="btn btn-link text-dark position-relative p-0"
          >
            <!-- cart -->
            <svg
              width="22"
              height="22"
              viewBox="0 0 16 16"
              fill="currentColor"
              xmlns="http://www.w3.org/2000/svg"
            >
              <path
                d="M0.5 1.5h2l1.5 8.5h8.5l1.5-6H3.5"
                fill="none"
                stroke="currentColor"
                stroke-width="1.5"
                stroke-linecap="round"
                stroke-linejoin="round"
              />
              <circle cx="6" cy="14" r="1" />
              <circle cx="12" cy="14" r="1" />
            </svg>
            <span
              class="position-absolute top-0 start-100 translate-middle badge rounded-pill bg-primary cart-badge"
              >0</span
            >
          </button>

          <a href="#" class="btn btn-primary px-4 fw-semibold">Get Started</a>
        </div>
      </div>
    </div>
  </nav>
</template>

<script setup lang="ts">
type DropdownItem = { label: string; href: string };
type DropdownGroup = { label: string; items: DropdownItem[] };

const dropdownGroups: DropdownGroup[] = [
  {
    label: "Home",
    items: [
      { label: "Home 1", href: "#" },
      { label: "Home 2", href: "#" },
      { label: "Home 3", href: "#" },
    ],
  },
  {
    label: "Courses",
    items: [
      { label: "All Courses", href: "#" },
      { label: "Course Details", href: "#" },
      { label: "Instructors", href: "#" },
    ],
  },
  {
    label: "Pages",
    items: [
      { label: "About", href: "#" },
      { label: "FAQ", href: "#" },
      { label: "Pricing", href: "#" },
    ],
  },
  {
    label: "Blog",
    items: [
      { label: "Blog List", href: "#" },
      { label: "Blog Single", href: "#" },
      { label: "Categories", href: "#" },
    ],
  },
];

const singleLink: { label: string; href: string } = {
  label: "Contact",
  href: "#",
};
</script>

<style lang="scss" scoped>
.navbar {
  padding-top: 0.75rem;
  padding-bottom: 0.75rem;
}

.nav-link {
  color: #0b1a33; // dark navy tone as in screenshot
}

.vr {
  width: 1px;
  height: 24px;
  background-color: rgba(0, 0, 0, 0.15);
}

.cart-badge {
  font-size: 0.65rem;
  min-width: 1.1rem;
  height: 1.1rem;
  display: inline-flex;
  align-items: center;
  justify-content: center;
}
</style>
