# Consumer–Provider Handshake

## Thông tin chung

- Lab: FIT4110 Lab 03
- Ngày: 2026-06-08
- Provider team: team-vision
- Consumer team: team-iot
- Provider service: AI Vision mock
- Consumer service: IoT Ingestion

## Contract

- Contract file: contracts/ai-vision.openapi.yaml
- Mock base URL: http://localhost:4011
- Auth method: Bearer token
- Endpoint được test: POST /detect

## Smoke test

### Request

```http
POST /detect
Authorization: Bearer {{authToken}}
Content-Type: application/json
```

```json
{
  "camera_id": "CAM01",
  "image_url": "https://example.com/frame.jpg"
}
```

### Expected response

```json
{
  "detection_id": "D-20260608-0001",
  "label": "person",
  "confidence": 0.87
}
```

## Kết quả

- [x] Consumer gọi mock thành công.
- [x] Consumer parse được field cần dùng.
- [x] Consumer hiểu lỗi 4xx/5xx provider trả về.
- [x] Có Newman report hoặc screenshot.

## Ghi chú thay đổi hợp đồng

| Nội dung | Trước | Sau | Người đồng ý |
|---|---|---|---|
| Mock URL | N/A | http://localhost:4011 | team-vision |
| Auth token | N/A | Bearer {{authToken}} | team-vision |

## Xác nhận

- Provider representative: team-vision lead
- Consumer representative: team-iot lead
