# math_app_policy

MathQuest 앱의 공개 정책 문서를 호스팅하는 저장소입니다 (GitHub Pages).

## 페이지

- 🏠 [메인](https://jjanghyoson.github.io/math_app_policy/)
- 🔒 [개인정보처리방침](https://jjanghyoson.github.io/math_app_policy/privacy_policy.html)
- 📄 [이용약관](https://jjanghyoson.github.io/math_app_policy/terms_of_service.html)
- 🗑️ [데이터 삭제 안내](https://jjanghyoson.github.io/math_app_policy/account_deletion.html)

Play Console 의 개인정보처리방침·데이터 삭제 URL 로 위 주소를 씁니다.
앱의 나 탭 → 앱 정보 화면에서도 같은 내용을 보여 주고 "웹 페이지로 보기"로 이 페이지를 엽니다.
**파일명을 바꾸면 앱과 Play Console 의 링크가 깨집니다.**

## 문서를 고칠 때

HTML 은 직접 고치지 않습니다. 원문은 앱 저장소의 `lib/policies.ts` 하나이고,
앱 화면과 이 페이지가 모두 그 파일에서 만들어집니다.

```bash
cd /workspace/mathapp/math_app
# 1) lib/policies.ts 수정 (최종 수정일 UPDATED_DATE 도 갱신)
npm run policy:build          # → ../math_policy/*.html 재생성
# 2) 두 저장소 모두 커밋·푸시 (앱 화면은 다음 앱 업데이트부터 반영)
```

내용은 앱의 실제 동작과 일치해야 합니다(사실과 다르면 Play 심사에서 문제가 됩니다).

| 앱에서 바뀌는 것 | 확인할 곳 |
|---|---|
| 저장 항목 | `lib/store.ts` (`STORAGE_KEYS`, 각 인터페이스) |
| 저장 위치 | `lib/local-db.ts` |
| 권한 | `app.config.ts` (`permissions`, `blockedPermissions`), `android/app/src/main/AndroidManifest.xml` |
| 삭제 경로 | `app/(tabs)/profile.tsx` (현재 학년 기록 초기화 · 모든 데이터 삭제) |
| 광고·분석·결제 SDK 추가 | `package.json` — 추가되면 방침과 Play 데이터 보안 답안을 함께 수정 |

## 문의

MathQuest 운영자 · jjanghyoson@gmail.com
