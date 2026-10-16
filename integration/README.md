# Denova integration notes

This is an independent API asset example and integration contract. It is not an official upstream provider, and the contract JSON is not a validated upstream settings import. API output validation is separate from in-app acceptance.

Pinned upstream SHA: b7895383d01abb311ba4bf2690dd1249a9156d26

- [internal/image/generation](https://github.com/alfredxw/denova/blob/b7895383d01abb311ba4bf2690dd1249a9156d26/internal/image/generation)
- [config/image_api_profiles.go](https://github.com/alfredxw/denova/blob/b7895383d01abb311ba4bf2690dd1249a9156d26/config/image_api_profiles.go)
- [internal/app/image/generation.go](https://github.com/alfredxw/denova/blob/b7895383d01abb311ba4bf2690dd1249a9156d26/internal/app/image/generation.go)

Images: authenticate with Bearer, submit once and persist the id, poll the image generations/{id} route, and download result.data[0].url. Resolution fields differ by model; changing Base URL alone is insufficient.

No native video-model entry point was verified for this project. This example covers image assets only.

In-app checklist: model selection → duplicate-safe submission → task recovery → save originals → import/display in the original UI → reconcile billing. Full upstream UI acceptance remains pending.
